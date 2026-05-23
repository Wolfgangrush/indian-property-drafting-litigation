# Changelog

All notable changes to the `indian-property-drafting` plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/) and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [0.2.2-alpha] — 2026-05-24

### Transactional-instrument reference.docx + output-pairing discipline

This plugin produces transactional instruments (contracts / conveyancing deeds), not pleadings. The v0.2.1 reference.docx wrongly applied the Bombay HC Nagpur pleading style (TNR 14pt 1.5 spacing, spaced + UNDERLINED bold-centered section headers, "MOST RESPECTFULLY SHEWETH:" anchor) — wholly inappropriate for commercial documents. v0.2.2 ships a correctly-calibrated transactional reference.docx.

### Added

- **Transactional `reference.docx`** at `skills/<base>/reference.docx` — TNR 12pt body, single line spacing, 2.5cm margins all around, Heading 1 bold centered (NOT underlined) for document title, Heading 2 bold left for section titles (e.g., "1. DEFINITIONS"), Heading 3 bold italic left for sub-sections, Heading 4 italic left for sub-sub-sections. No spaced section headers. No underlining of headings. Page numbers bottom-center.
- **`build_reference_docx.py`** (transactional variant) — reproducible build script for the transactional reference.docx.
- **`pair_md_to_docx.sh`** — helper script that every agent calls after writing a `.md` output. Pairs every Markdown artifact with a `.docx` using the shipped reference.docx + the post-pandoc table-width fix.
- **OUTPUT-PAIRING DISCIPLINE** section in `_drafting_common/SKILL.md` documenting the per-agent output-pairing map and the helper-script usage.

### Changed

- **reference.docx style** for transactional instruments is now correctly differentiated from pleading style. Pleading-style v0.2.1 reference.docx is REMOVED from this plugin and replaced with the transactional variant.
- **Pipeline output convention** — every agent's `.md` output is now paired with a `.docx`. Advocates do not natively read Markdown; every artifact is opened in Word.

### Migration

Any existing case folders that produced output under v0.2.1 should re-run the Drafter to produce the corrected `.docx` files in the transactional style. The `.md` source files remain unchanged.

---

## [0.2.1-alpha] — 2026-05-24

### Filing-grade render-defect repair + pipeline-optionality

The v0.1.0 render path produced filing-grade Markdown but the pandoc → `.docx` conversion failed Bombay HC / equivalent Registry expectations on multiple counts (title not bold, section headers left-aligned, Index table column-headers wrapping vertically, party block leaking onto cover pages, ~6,200-word bloat). This release repairs the render path, calibrated against an actual filed Bombay HC Nagpur Second Appeal pleading the author supplied as the filing-grade reference. Inherits the v0.2.1 fixes from `indian-hc-drafting-litigation`.

### Added

- **Pre-customised `reference.docx`** in the plugin's base-skill folder with locked Word styles (TNR 14pt body, 1.5 line spacing, 4cm left / 2.5cm right-top-bottom margins, Heading 1 bold centered, Heading 2 bold + UNDERLINED + centered + letter-spacing for the spaced `F A C T S` effect, Heading 3 bold + UNDERLINED + centered for unspaced section headers, Heading 4 bold + UNDERLINED + left for `MOST RESPECTFULLY SHEWETH:` style anchors, fixed table layout).
- **`build_reference_docx.py`** — reproducible python-docx build script for the shipped reference.docx.
- **`fix_docx_tables.py`** — post-pandoc Python script that forces column widths on every table (5-col 8/8/60/14/10; 4-col 10/10/65/15; 3-col 10/75/15; 2-col 18/82). Locks first-row bold + centered + vertically-centered cells. Drafter runs this as the final post-pandoc step.
- **MARKDOWN HEADING DISCIPLINE** in the Drafter prompt + base SKILL.md (Heading 1 / Heading 2 / Heading 3 / Heading 4 mapping for court header / spaced section headers / unspaced section headers / left-anchored headings).
- **VERBOSITY DISCIPLINE** with per-case-type word-count targets and hard ceilings.
- **PIPELINE-OPTIONALITY** — Verifier / Refiner / Overseer now OPTIONAL QC layers. Default exit point is after Stage 3 (Drafter).
- **COVER-PAGE DISCIPLINE** — INDEX / SYNOPSIS / LIST OF ANNEXURES each begin on `\newpage` with short cause-title only.
- **Bold-number paragraph convention** — Facts and Grounds paragraphs use `**1.** **2.** **3.**`.
- **Inline-bold highlighting convention** for property descriptors / annexure markers / key terms within Facts narrative.

### Changed

- **Drafter pandoc command** is now TWO steps (pandoc → .docx, then `fix_docx_tables.py`). Step 2 is non-negotiable; skipping it reproduces the v0.2.0 stacking-column defect.

### Cost / token-budget note

Running the full 6-agent pipeline burns approximately 600K tokens per draft, which can exhaust an advocate's Claude session limit. v0.2.1 makes Stages 4–6 OPTIONAL so a baseline Reader → Format → Drafter run (~280K tokens) is sufficient for routine pleadings. The optional QC stages remain available for high-stakes matters.

---

## [0.1.0-alpha] — 2026-05-16 (initial release)

### Added

- **Plugin scaffolding** — `.claude-plugin/plugin.json` manifest · MIT `LICENSE` · `NOTICE.md` provenance and privilege statement · `.gitignore` · this `CHANGELOG.md` · comprehensive `README.md`.
- **Six-agent drafting pipeline** — Reader → Format → Drafter → Verifier → Refiner → Overseer. Each agent is a markdown file under `agents/<name>/<name>.md` with YAML frontmatter declaring `name`, `description`, and `allowed-tools`.
- **Shared infrastructure skills:**
  - `_drafting_common` — anti-pollution rules, encoding standards, language conventions, AI-style-marker blacklist, property-specific privacy firewall (party names, property descriptions, consideration figures, Ready Reckoner values), Indian Stamp Act 1899 + applicable State Stamp Act schedule discipline (Article-wise tabular reference), Registration Act 1908 compulsory-registration discipline read with Section 17(1)(a)-(d) and Section 17(1A) read with Section 53A TPA 1882, the *Suraj Lamp & Industries v. State of Haryana* (2012) 1 SCC 656 discipline (GPA-Sale / Agreement-to-Sell-with-Possession-and-GPA does NOT convey title), the Sub-Registrar circle discipline, the Ready Reckoner / Market Value rates for stamp-duty discipline, the Section 32A Registration Act enquiry-into-stamp-duty discipline, the Section 27 Indian Stamp Act 1899 facts-affecting-stamp-duty discipline, mutation discipline (Section 35 Land Records / state-specific), personal-law overlays (Hindu Succession Act 1956 coparcener overlay, Indian Succession Act 1925 testamentary overlay, Mussalman Personal Law (Shariat) Application Act 1937 overlay for Muslim heirs, Hindu Joint Family discipline for partition).
  - `_property_drafting_base` — universal Indian property-instrument skeleton (Title -> Parties block with PAN / Aadhaar references / family-tree where relevant -> Recitals with title-chain narrative -> Operative clauses -> Schedule of Property with municipal / survey / Ready Reckoner reference -> Encumbrance / Title warranties -> Stamping note -> Registration note -> Witnesses -> Signatures).
- **Ten case-type skill scaffolds:**
  - `gift-deed-draft` — Gift Deed under Sections 122-129 of the Transfer of Property Act 1882 + Section 17(1)(a) Registration Act 1908 (compulsorily registrable) + State Stamp Act concessional rates for family-member gifts
  - `exchange-deed-draft` — Exchange Deed under Sections 118-121 TPA 1882 + Section 17(1)(b) Registration Act 1908 + dual-stamp discipline (each leg of the exchange separately stamped)
  - `release-deed-draft` — Release Deed for relinquishment of rights / share in immovable property; common between coparceners post-partition or between joint-tenants
  - `private-trust-deed-draft` — Private Trust Deed under the Indian Trusts Act 1882 (Sections 3-9, 14-30) — settlor / trustees / beneficiaries / trust property / trust purposes / trustee powers and duties / beneficiary rights / accounts and audit / variation and termination
  - `wakf-deed-draft` — Wakf Deed (Wakf-bil-Mall / Wakf-bil-Wasiyat / Wakf-alal-Aulad) under the Wakf Act 1995 read with the Mussalman Wakf Validating Act 1913; State Wakf Board registration discipline
  - `easement-deed-draft` — Easement Deed under the Indian Easements Act 1882 — easement of right of way / easement of light and air / easement of support / easement of water / quasi-easement upon severance of unity of ownership
  - `partition-deed-draft` — private Partition Deed between coparceners / co-owners of joint-family / joint-tenancy property under TPA / Hindu Succession Act 1956 read with Hindu Mitakshara / Dayabhaga schools or Muslim succession discipline; Section 7 Indian Stamp Act 1899 partition discipline
  - `settlement-deed-draft` — Family Settlement Deed — *Kale v. Deputy Director of Consolidation* (1976) 3 SCC 119 framework — antecedent title not required to be proved; mutual relinquishment with public-document recognition; Section 17 Registration Act 1908 framework + State Stamp Act concessional rates
  - `mortgage-deed-draft` — Registered Mortgage Deed under Section 59 read with Section 58 TPA 1882; six TPA mortgage types covered (simple mortgage / mortgage by conditional sale / usufructuary mortgage / English mortgage / equitable mortgage by deposit of title deeds / anomalous mortgage); Section 67 right of foreclosure / sale / suit framework
  - `title-investigation-report-draft` — Title Investigation Report / Title Search Memorandum — title chain back to 30 years (where the title has been with the same family) or to mother deed; encumbrance certificate analysis from the Sub-Registrar's office; mutation entries; revenue records cross-check; pending litigation / charge / lis pendens; marketable title opinion with risk-flag listing
- **State-aware design** — `state-config/exemplars/` provides State-specific Stamp Act schedule references, Ready Reckoner / Market Value framework, Sub-Registrar circle conventions, applicable State land-records / mutation framework, family-member concessional stamp duty rules, and applicable State Wakf Board / Charity Commissioner reference per State.

### Notes on this release

This is a **v0.1.0-alpha scaffold release**. The structural skeletons, agent pipeline, base skills, and 10 case-type skill frames are in place. Deep per-skill encoding (full clause libraries for each instrument type, State-specific stamp-duty calculations integrated with current Ready Reckoner values, deeper personal-law overlays for Muslim / Christian / Parsi succession matters, integration with State-specific land-records and mutation portals, and bench-specific Practice Directions for the Sub-Registrar circles in major cities) will land in v0.1.0 and onward.

### Released under

MIT License. Authored by Rushikesh R. Mahajan, Advocate, publishing under the Wolfgang Rush open-source brand for legal-tech infrastructure.
