# indian-property-drafting

> **Open-source Claude-compatible plugin for drafting Indian property, conveyancing, and estate instruments — the conveyancing-and-family-property side that complements `indian-contracts-drafting`'s commercial-contracts focus.**
>
> Six-agent drafting pipeline · ten instrument-type skills · deed-config-aware + state-config-aware · Transfer of Property Act 1882 + Registration Act 1908 + Indian Stamp Act 1899 + applicable State Stamp Acts + Indian Easements Act 1882 + Indian Trusts Act 1882 + Wakf Act 1995 + Hindu Succession Act 1956 + Indian Succession Act 1925 + Mussalman Personal Law (Shariat) Application Act 1937 + Suraj Lamp (2012) discipline + Kale (1976) family-settlement framework + Bharatiya Sakshya Adhiniyam 2023 discipline encoded.
>
> Released under MIT. Open infrastructure for the legal community. No commercial engagement offered through this repository — see Disclaimer below.

> ⚠️ **AI can make mistakes. Always verify the output.**
>
> This software generates assistive drafts and suggestions only. Every legal claim, citation, statute reference, procedural step, deadline calculation, and ground of relief must be independently verified by a qualified human practitioner before filing, advising a client, or relying on the output. The publisher accepts no liability for outputs used without verification.

> 🛡️ **Privacy primitive (ecosystem):** PII pseudonymisation across the Wolfgang Rush legal-tech family is handled via [pseudonymisation-gateway](https://github.com/Wolfgangrush/pseudonymisation-gateway) (MIT). When this drafting plugin is used inside an AI Law Firm built on that gateway, client PII is stripped before any cloud-LLM call and restored on response.


---

## Table of contents

1. [What this plugin does](#what-this-plugin-does)
2. [Instrument-type skills (full inventory with statutory authority)](#instrument-type-skills-full-inventory-with-statutory-authority)
3. [The 6-agent drafting pipeline (what each agent does)](#the-6-agent-drafting-pipeline)
4. [Installation](#installation) — Claude Desktop application
5. [Your first deed — step-by-step walkthrough](#your-first-deed--step-by-step-walkthrough)
6. [The `deed-config.md` file](#the-deed-configmd-file)
7. [State coverage and the `state-config/exemplars` layer](#state-coverage-and-the-state-configexemplars-layer)
8. [Built-in compliance disciplines](#built-in-compliance-disciplines)
9. [Privacy firewall — extra discipline for property content](#privacy-firewall--extra-discipline-for-property-content)
10. [Why MIT License](#why-mit-license)
11. [Sibling plugins](#sibling-plugins)
12. [Why this exists](#why-this-exists)
13. [Roadmap](#roadmap)
14. [Contributing](#contributing)
15. [Contact](#contact)
16. [Author and brand](#author-and-brand)
17. [Provenance and privilege statement](#provenance-and-privilege-statement)
18. [Disclaimer and Bar Council of India Rule 36 compliance](#disclaimer-and-bar-council-of-india-rule-36-compliance)
19. [License](#license)

---

## What this plugin does

This plugin lets an Indian advocate, sitting inside the Claude Desktop application, point at a deal folder on disk and obtain a complete property / conveyancing / estate instrument in `.docx` form — Title, Parties, Recitals with title-chain narrative, Operative Clauses (instrument-type-specific), Schedule of Property, Encumbrance / Title warranties, Stamping note, Registration note, Witnesses, Signatures — formatted in the State Stamp Act + Ready Reckoner regime, sourced from a `deed-config.md` file the user places in the deal folder and a `state-config/exemplars/<state>.md` exemplar.

The pipeline is six agents running in sequence:

1. **Reader** — extracts deed-facts (parties, title chain, Schedule of Property, encumbrance, consideration, personal-law overlay) from the deal folder with a per-document audit log, and applies the **property-specific privacy firewall** (every party name, PAN/Aadhaar, Survey/Municipal No., Sub-Registrar reference, consideration figure, Ready Reckoner value, mutation entry, and family-tree name substituted with structural placeholders before downstream AI processing).
2. **Format** — loads the instrument-type skill template, reads `deed-config.md` and the relevant State exemplar, and pre-substitutes State Stamp Act + applicable Article + Ready Reckoner / Market Value formula + Sub-Registrar circle + registration-fee schedule + personal-law overlay + mutation-route framework into a `format-shell.md`.
3. **Drafter** — writes the actual deed: Title + Parties + Recitals with title-chain + Operative Clauses (instrument-type-specific) + Schedule of Property + Encumbrance / Title warranties + Stamping note + Registration note + Witnesses + Signatures, in the formal Indian conveyancing register.
4. **Verifier** — anti-hallucination firewall **plus** Section 17 Registration Act compulsory-registration check **plus** Section 122-129 TPA gift-essentials **plus** *Suraj Lamp* (2012) GPA-sale-forbidden check **plus** Section 53A TPA agreement-to-sell discipline **plus** State Stamp Act schedule cross-foot **plus** Ready Reckoner cross-foot **plus** personal-law overlay check (Hindu coparcener post-2005 / Mussalman Shariat / Christian-Parsi ISA) **plus** Section 7 Indian Stamp Act partition discipline **plus** *Kale* family-settlement framework **plus** Indian Trusts Act three-certainties **plus** Wakf Act 1995 wakf-essentials + Section 36 registration **plus** Section 60 TPA mortgage-redemption discipline **plus** title-chain back to 30 years.
5. **Refiner** — applies Verifier flags, polishes language to formal Indian conveyancing register (*"THIS DEED WITNESSETH"*, *"TO HAVE AND TO HOLD"*, *"FOR EVER QUITCLAIMS AND RELEASES"*), enforces internal numbering and Schedule cross-reference consistency, strips AI-style markers, and re-substitutes real party names, real Survey numbers, real Sub-Registrar references, and real consideration figures into the final `.docx` (strictly on the user's local machine).
6. **Overseer** — reads the polished draft with an opposing-party / opposing-counsel lens (aggrieved family heir / creditor / mortgagee / Sub-Registrar refusing registration / Stamp Authority under-valuation challenge). Flags attackable Gift acceptance gaps, Trust certainty defects, Wakf perpetuity-in-purpose defects, Partition share-of-aggregate mis-foot, Settlement *Kale*-framework gap, Mortgage clog-on-redemption, easement quasi-easement-on-severance miscoupling, title-chain breaks, encumbrance non-disclosure, and Stamp Act under-valuation.

The output is what an advocate would put before the Sub-Registrar for registration — **not a template. Not a checklist. A deed** — ready for the advocate's review, professional verification, signature, stamping, and registration.

---

## Instrument-type skills (full inventory with statutory authority)

The plugin ships with ten instrument-type skills, each covering a distinct property / conveyancing / estate instrument:

### 1. `gift-deed-draft`

**Statutory authority:** TPA 1882 Sections 122-129 (definition, mode of execution, revocation) + Registration Act 1908 Section 17(1)(a) (COMPULSORILY REGISTRABLE) + Indian Stamp Act 1899 Article 34 + State Stamp Act concessional rates for blood-relative donees. **Use case:** voluntary transfer of property by Donor to Donee without consideration. **Output:** complete Gift Deed with natural-love-and-affection recital, granting clause, mandatory Donee-acceptance during Donor's lifetime (Section 122 + 129), possession clause, two-witness attestation (Section 123 — MANDATORY, non-curable).

### 2. `exchange-deed-draft`

**Statutory authority:** TPA 1882 Sections 118-121 + Registration Act 1908 Section 17(1)(b) + Indian Stamp Act Article 32 + **dual-stamp discipline** (each leg separately stamped). **Use case:** mutual transfer of property between Parties (barter of immovable properties; cash equalisation optional). **Output:** complete Exchange Deed with mutual-transfer clauses, equality-of-value / cash-equalisation recital, Section 119 TPA mutual rights/liabilities, Section 120 TPA defect-deprivation remedy.

### 3. `release-deed-draft`

**Statutory authority:** Section 17(1)(b) Registration Act 1908 + Indian Stamp Act Article 55 + State Stamp Act concessional rates for blood-relative releasor/releasee. **Use case:** Releasor relinquishes share/right/title/interest in immovable property in favour of co-owner/Releasee (typically post-partition, between coparceners, between joint-tenants). **Output:** complete Release Deed with FOR-EVER-QUITCLAIMS-AND-RELEASES register, pre-existing-joint-right recital, indemnity, no-further-claim waiver.

### 4. `private-trust-deed-draft`

**Statutory authority:** Indian Trusts Act 1882 Sections 3-30 — three-certainties rule (Section 6 + 9: intention + property + beneficiary + purpose) + Section 5 (immovable-property trusts require registered instrument) + Sections 14-30 (trustee powers and duties) + Sections 56-65 (variation / termination). **Use case:** Settlor declares private trust for named/described beneficiaries, transferring trust corpus to named Trustees. **Output:** complete Trust Deed with three-certainties pleading, trust corpus, trust purposes, trustee appointment + succession + powers + duties, accounts/audit framework, variation/termination clauses.

### 5. `wakf-deed-draft`

**Statutory authority:** Wakf Act 1995 (Section 3(r) definition + Section 36 registration + Sections 51-52 alienation restrictions + Section 83 Wakf Tribunal) + Mussalman Wakf Validating Act 1913 (validates wakf-alal-aulad) + Mussalman Personal Law (Shariat) Application Act 1937 + *Mahomed Mohsin v. Sahib Bakar* (perpetuity-in-ultimate-purpose). **Use case:** Wakif's permanent dedication of property to Almighty Allah for religious/pious/charitable/family purposes. **Output:** complete Wakf Deed (Wakf-bil-Mall / Wakf-bil-Wasiyat / Wakf-alal-Aulad) with mandatory perpetuity-in-ultimate-purpose clause, mutawalli appointment + succession, State Wakf Board registration undertaking, Sunni/Shia sub-school nuances.

### 6. `easement-deed-draft`

**Statutory authority:** Indian Easements Act 1882 — Section 4 definition + Section 5 classifications + Sections 7-12 acquisition + Section 13 quasi-easement upon severance + Section 15 prescription (20 years) + Section 35 extinguishment + Section 52 easement-vs-licence distinction. **Use case:** Servient Owner grants easement (right of way / light and air / water / support / drainage) to Dominant Owner. **Output:** complete Easement Deed with dominant + servient tenement identification, easement nature with classifications, manner of enjoyment, servient owner obligations, disturbance + remedy clauses.

### 7. `partition-deed-draft`

**Statutory authority:** TPA 1882 + Hindu Succession Act 1956 (Sections 6, 8 + post-2005 daughter-coparcener amendment + *Vineeta Sharma v. Rakesh Sharma* (2020) 9 SCC 1) + Mussalman Personal Law (Shariat) Application Act 1937 + Indian Succession Act 1925 + **Section 7 Indian Stamp Act 1899** (highest-share-aggregate-rate basis) + State Stamp Act concessions for coparceners. **Use case:** private partition between coparceners / co-owners outside court (distinct from a partition suit under Order 34 CPC). **Output:** complete Partition Deed with joint-ownership recital, pre-partition shares, intent-to-partition, metes-and-bounds allotment to each Party, equality-adjustment cash recital, extinguishment of joint rights.

### 8. `settlement-deed-draft`

**Statutory authority:** *Kale v. Deputy Director of Consolidation* (1976) 3 SCC 119 framework (five ingredients: bona-fide arrangement / mutual relinquishment / antecedent claims / no need to prove antecedent title / public-document recognition) + Section 17(1)(b) Registration Act 1908 + Indian Stamp Act Article 58 + State concessional rates. **Use case:** family settlement among family members to resolve existing/future disputes by mutual relinquishment of contesting claims. **Output:** complete Family Settlement Deed with family-relationship recital, antecedent-claims-and-disputes recital, *Kale*-framework recital, settlement-terms with each Family Member's recognised rights, no-third-party-claim covenant.

### 9. `mortgage-deed-draft`

**Statutory authority:** TPA 1882 Section 58 (six mortgage types — simple / conditional sale / usufructuary / English / equitable by deposit of title deeds / anomalous) + Section 59 (mode of execution: registered + two witnesses for non-equitable) + Section 60 (right of redemption — *Murarilal v. Devkaran* no-clog discipline) + Section 67 (foreclosure / sale) + Indian Stamp Act Article 40 (ad valorem on secured amount) / Article 6 (equitable mortgage memorandum, lower rate). **Use case:** Mortgagor creates registered mortgage to secure debt/loan to Mortgagee. **Output:** complete Mortgage Deed with mortgage-type declaration, Mortgagor's covenants, Default + Mortgagee's-rights clauses (SARFAESI / IBC / Order 34 CPC cross-references where applicable), mandatory **no-clog-on-redemption** clause, re-conveyance-on-redemption clause.

### 10. `title-investigation-report-draft`

**Statutory authority:** Indian conveyancing practice + Registration Act 1908 + Limitation Act 1963 Articles 64, 65 (12-year limitation for possession on title / on dispossession) + RERA 2016 (for under-construction projects) + State land-records framework. **Use case:** Title due-diligence opinion produced for a purchaser / mortgagee / financier before completing a transaction — a LEGAL OPINION document, NOT a registered instrument. **Output:** complete Title Investigation Report with engagement details, property description, documents examined, methodology, title-chain narrative (back 30 years / to mother deed), encumbrance certificate analysis, mutation entries cross-check, litigation search, statutory dues clearance, RERA compliance, marketable-title opinion (MARKETABLE / WITH RESERVATIONS / NOT MARKETABLE), risk flags classified by severity, reservations.

### Shared infrastructure skills

- **`_drafting_common`** — anti-pollution rules, property privacy firewall, AI-style-marker blacklist (with conveyancing-register preservation — *"hereby"* and *"thereby"* are STANDARD in conveyancing, preserved), citation discipline, **Indian Stamp Act 1899 + State Stamp Act schedule discipline**, **Registration Act 1908 + Section 17 / 17(1A) + Section 49 / Section 53A TPA discipline**, ***Suraj Lamp* (2012) discipline** (mandatory), ***Kale* (1976) Family Settlement framework**, **Section 7 Indian Stamp Act partition discipline**, **Indian Trusts Act 1882 three-certainties rule**, **Wakf Act 1995 + Mussalman Wakf Validating Act 1913 wakf-essentials**, **Indian Easements Act 1882 dominant-servient-tenement rule**, **personal-law overlays** (HSA 1956 with post-2005 daughter-coparcener amendment / Mussalman Shariat 1937 / ISA 1925 Christian-Parsi), **Limitation Act 1963 Article map for property suits**.
- **`_property_drafting_base`** — universal Indian property-instrument skeleton (Title -> Parties block -> Recitals with title-chain -> Operative Clauses -> Schedule of Property -> Encumbrance/Title warranties -> Stamping note -> Registration note -> Witnesses -> Signatures).

---

## The 6-agent drafting pipeline

| Agent | What it reads | What it writes | Key property-domain specialisation |
|---|---|---|---|
| **`reader`** | Every file in the deal folder + the instrument-type skill's expected exhibits list | `deed-facts.md` with per-document audit log + privacy-firewalled placeholder mapping in the header | Privacy firewall — substitutes party names + PAN/Aadhaar + Survey/Municipal numbers + consideration figures + Ready Reckoner values + mutation entries + family-tree names before downstream AI processing |
| **`format`** | `deed-facts.md` + `deed-config.md` + instrument-type SKILL.md + `_property_drafting_base` + State exemplar | `format-shell.md` with State Stamp Act + applicable Article + Ready Reckoner formula + Sub-Registrar circle + personal-law overlay pre-substituted | Resolves State Stamp Act and applicable Article per instrument-type; loads Ready Reckoner / Circle Rate / Guidance Value / Jantri framework |
| **`drafter`** | `deed-facts.md` + `format-shell.md` + instrument-type SKILL.md + `_property_drafting_base` + law PDFs + State exemplar | `draft-v1.md` + `draft-v1.docx` | Writes Title + Parties + Recitals (title-chain narrative) + Operative Clauses + Schedule + Encumbrance Warranties + Stamping note + Registration note + Witnesses + Signatures in formal conveyancing register; applies *Suraj Lamp* discipline (refuses GPA-Sale variants) |
| **`verifier`** | `draft-v1.md` + `deed-facts.md` + `deed-config.md` + law PDFs + State exemplar | `verification-report.md` | Anti-hallucination + Section 17 Registration Act + Section 122-129 TPA gift-essentials + *Suraj Lamp* + Section 53A TPA + State Stamp Act cross-foot + Ready Reckoner cross-foot + personal-law overlay + Section 7 ISA partition + *Kale* family-settlement + Indian Trusts Act three-certainties + Wakf Act + Section 60 TPA no-clog + title-chain |
| **`refiner`** | `draft-v1.md` + `verification-report.md` + `deed-config.md` + `deed-facts.md` | `draft-v2.md` + `draft-v2.docx` | Polish to formal Indian conveyancing register + internal numbering / Schedule cross-reference / defined-term consistency + privacy-firewall reversal (real values re-substituted from local mapping into final `.docx`) + stamping-and-registration-ready output |
| **`overseer`** | `draft-v2.docx` + `deed-facts.md` + `deed-config.md` | `opposing-notes.md` + `final-draft.docx` | Opposing-party / Sub-Registrar / Stamp Authority critique — Gift acceptance gaps, Trust certainty defects, Wakf perpetuity-in-purpose, Partition share-aggregate mis-foot, Settlement *Kale*-framework gap, Mortgage clog-on-redemption, title-chain breaks, encumbrance non-disclosure, Stamp Act under-valuation |

---

## Installation

This is a Claude-compatible plugin in the Anthropic plugin format, designed to run inside the **Claude Desktop application** (available at <https://claude.ai/download>). The plugin folder location depends on your OS:

| OS | Plugin folder path |
|---|---|
| **macOS** | `~/Library/Application Support/Claude/plugins/` |
| **Windows** | `%APPDATA%\Claude\plugins\` |
| **Linux** | `~/.config/Claude/plugins/` |

Clone the plugin into that folder:

```bash
# macOS / Linux
cd ~/Library/Application\ Support/Claude/plugins
git clone https://github.com/Wolfgangrush/indian-property-drafting-litigation.git indian-property-drafting

# Windows (PowerShell)
cd $env:APPDATA\Claude\plugins
git clone https://github.com/Wolfgangrush/indian-property-drafting-litigation.git indian-property-drafting
```

Restart the Claude Desktop application. The plugin is auto-discovered on the next session start.

### Verifying the install

In a Claude session, type:

- *"draft gift deed"* — triggers `gift-deed-draft`
- *"draft exchange deed"* — triggers `exchange-deed-draft`
- *"draft release deed"* — triggers `release-deed-draft`
- *"draft trust deed"* — triggers `private-trust-deed-draft`
- *"draft wakf deed"* — triggers `wakf-deed-draft`
- *"draft easement deed"* — triggers `easement-deed-draft`
- *"draft partition deed"* — triggers `partition-deed-draft`
- *"draft family settlement"* — triggers `settlement-deed-draft`
- *"draft mortgage deed"* — triggers `mortgage-deed-draft`
- *"draft title investigation report"* — triggers `title-investigation-report-draft`

---

## Your first deed — step-by-step walkthrough

Suppose you wish to draft a **Gift Deed** of a residential flat in Mumbai from a father (Donor) to his son (Donee) — concessional family-member stamp duty.

### Step 1 — create a deal folder

```
~/Desktop/deals/
└── gift-deed-2026-FAMILY-MATTER/
    ├── deed-config.md          ← declares State + instrument type + parties + Schedule
    ├── inputs/
    │   ├── donor-pan.pdf
    │   ├── donor-aadhaar.pdf
    │   ├── donee-pan.pdf
    │   ├── donee-aadhaar.pdf
    │   ├── relationship-proof-birth-certificate.pdf
    │   ├── original-sale-deed-of-flat.pdf
    │   ├── encumbrance-certificate-30-year.pdf
    │   ├── society-NOC-for-transfer.pdf
    │   ├── property-tax-clearance.pdf
    │   └── ready-reckoner-extract.pdf
    └── laws/
        ├── transfer-of-property-act-1882.pdf
        ├── registration-act-1908.pdf
        ├── maharashtra-stamp-act-1958.pdf
        └── hindu-succession-act-1956.pdf
```

### Step 2 — write `deed-config.md`

```yaml
instrument_type: "gift-deed"
state: "maharashtra"
sub_registrar_office: "Mumbai City — Sub-Registrar Circle ___"
ready_reckoner_value: "[RR-Value-Placeholder]"
consideration: "nil (natural love and affection)"
applicable_state_stamp_act: "Maharashtra Stamp Act 1958"
stamp_article: "Article 34"
family_member_concessional_rate: true
relationship: "father_to_son"
personal_law: "hindu"
property_type: "flat_in_cooperative_housing_society"
society_consent_obtained: true
parties:
  - role: "Donor"
    party_name: "[Donor-Placeholder]"
  - role: "Donee"
    party_name: "[Donee-Placeholder]"
```

### Step 3 — invoke the plugin

Open Claude Desktop, navigate to the deal folder, and type:

> *draft gift deed*

The pipeline runs through Reader → Format → Drafter → Verifier → Refiner → Overseer and outputs `final-draft.docx` ready for execution + stamping + registration.

---

## The `deed-config.md` file

Minimum fields: `instrument_type` · `state` · `sub_registrar_office` · `ready_reckoner_value` · `consideration` · `applicable_state_stamp_act` · `stamp_article` · `family_member_concessional_rate` · `relationship` · `personal_law` · `property_type` · `parties`. Instrument-type-specific fields layer on top — see each instrument-type SKILL.md.

`.gitignore` excludes `deed-config.md` and `deed-facts.md` from any git repo.

---

## State coverage and the `state-config/exemplars` layer

The `state-config/exemplars/` folder contains one Markdown file per supported State, encoding:

- The applicable State Stamp Act + Schedule I Article-wise stamp duty for each instrument type
- The Ready Reckoner / Circle Rate / Guidance Value / Jantri / Market Value framework + portal
- Sub-Registrar circle conventions
- Mutation / revenue records framework
- State-specific Apartment Ownership / Co-operative Societies / RERA / Land Reforms overlays
- *Suraj Lamp* enforcement status

Initial coverage in v0.1.0-alpha: Maharashtra · Karnataka · Tamil Nadu · Delhi · UP · Gujarat · West Bengal · Telangana. AP · Kerala · Rajasthan · MP · Odisha · Punjab · Haryana · Bihar · the North-Eastern States in v0.1.x.

---

## Built-in compliance disciplines

See `skills/_drafting_common/SKILL.md` for the full discipline framework. Headline disciplines:

- **Section 17 Registration Act 1908 compulsory-registration discipline** — every property instrument compulsorily registrable; Section 49 consequence of non-registration; collateral-purpose-evidence exception
- **Indian Stamp Act 1899 + applicable State Stamp Act schedule cross-foot** — instrument-type and State-specific
- ***Suraj Lamp & Industries v. State of Haryana* (2012) 1 SCC 656 discipline** — GPA-Sale / Agreement-to-Sell-with-Possession-and-GPA / Will-with-GPA combinations DO NOT convey title; the Drafter refuses to draft such instruments
- **Section 53A TPA agreement-to-sell discipline** — post-2001 registrability under Section 17(1A) Registration Act; part-performance protection requires written-and-signed + reasonable certainty + possession/payment/readiness
- ***Kale v. Deputy Director* (1976) 3 SCC 119 framework** — five ingredients for valid Family Settlement
- **Section 7 Indian Stamp Act 1899 partition discipline** — highest-share-aggregate-rate
- **Indian Trusts Act 1882 three-certainties rule** — Section 6 + 9
- **Wakf Act 1995 + Mussalman Wakf Validating Act 1913 wakf-essentials** — permanent dedication / religious-pious-charitable purposes / mutawalli / Section 36 registration / perpetuity-in-ultimate-purpose (*Mahomed Mohsin v. Sahib Bakar*)
- **Section 60 TPA no-clog-on-redemption discipline** — *Murarilal v. Devkaran*
- **Personal-law overlays** — HSA 1956 + post-2005 daughter-coparcener (*Vineeta Sharma* 2020) / Mussalman Personal Law (Shariat) 1937 / ISA 1925
- **Title-chain back to 30 years discipline** for Title Investigation Reports
- **Bharatiya Sakshya Adhiniyam 2023 transition** — Section 65B IEA → Section 63 BSA

---

## Privacy firewall — extra discipline for property content

Property instruments contain highly sensitive material — KYC, PAN, Aadhaar, family-tree relationships, Survey/Municipal numbers, consideration figures, Ready Reckoner values, mutation entries. The plugin's privacy discipline:

1. **Reader** substitutes every party name, PAN, Aadhaar, Survey No., Municipal No., Sub-Registrar registration reference, consideration figure, Ready Reckoner value, mutation entry, and family-tree name with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `deed-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw property descriptions or raw consideration figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `deed-facts.md` and `deed-config.md` so they cannot be committed accidentally.

---

## Why MIT License

The MIT licence is the most permissive widely-recognised open-source licence. The accompanying `NOTICE.md` does not modify the licence — it documents the provenance and the privilege position so that any future audit can verify the plugin's clean origin.

---

## Sibling plugins

This plugin is one in the **Wolfgang Rush** family of Indian legal-drafting plugins. All thirteen siblings ship under the same six-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) and the family-of-plugins doctrine — each plugin narrowly scoped to one practice area / forum:

| Plugin | GitHub repo | Scope |
|---|---|---|
| `supreme-court-drafting` | [supreme-court-drafting-litigation](https://github.com/Wolfgangrush/supreme-court-drafting-litigation) | SLPs · Writ Art 32 · Transfer · Review · Curative — Supreme Court of India |
| `indian-hc-drafting` | [indian-hc-drafting-litigation](https://github.com/Wolfgangrush/indian-hc-drafting-litigation) | Pleadings across all 25 Indian High Courts (bench-config-aware) |
| `district-court-drafting` | [district-court-drafting-litigation](https://github.com/Wolfgangrush/district-court-drafting-litigation) | Plaints · WS · CPC applications · BNSS complaints across 25+ States (state-config) |
| `indian-family-drafting` | [indian-family-drafting-litigation](https://github.com/Wolfgangrush/indian-family-drafting-litigation) | HMA · SMA · IDA · matrimonial · custody · DV Act · maintenance · adoption |
| `indian-contracts-drafting` | [indian-contracts-drafting-litigation](https://github.com/Wolfgangrush/indian-contracts-drafting-litigation) | MSA · NDA · employment · lease · sale · GPA · SHA · will · loan · arbitration |
| `indian-banking-drafting` | [indian-banking-drafting-litigation](https://github.com/Wolfgangrush/indian-banking-drafting-litigation) | DRT · SARFAESI · NI Act 138 · IBC §7 / §95 · DRAT |
| `indian-labour-drafting` | [indian-labour-drafting-litigation](https://github.com/Wolfgangrush/indian-labour-drafting-litigation) | ID Act · POSH · PG · EPF · ESI · MW · IESO + State exemplars |
| `indian-property-drafting` (this) | [indian-property-drafting-litigation](https://github.com/Wolfgangrush/indian-property-drafting-litigation) | Gift · Exchange · Release · Trust · Wakf · Easement · Partition · Settlement · Mortgage · TIR |
| `indian-company-drafting` | [indian-company-drafting](https://github.com/Wolfgangrush/indian-company-drafting) | NCLT (241/242 · 245 · 230-232 · 66 · 252 · 213) · NCLAT (421 + 61) · IBC §9 / §10 |
| `indian-tax-drafting` | [indian-tax-drafting](https://github.com/Wolfgangrush/indian-tax-drafting) | Form 35 CIT(A) · Form 36 ITAT · Form 10A · Sec 148A · 263/264 · 271/270A · 144C · 201 · 260A |
| `indian-consumer-drafting` | [indian-consumer-drafting](https://github.com/Wolfgangrush/indian-consumer-drafting) | District / State / NCDRC + medical-negligence + product liability |
| `indian-mact-drafting` | [indian-mact-drafting](https://github.com/Wolfgangrush/indian-mact-drafting) | MV Act 1988 (2019 amended) · Sarla Verma + Pranay Sethi · state-config |
| `indian-ip-drafting` | [indian-ip-drafting](https://github.com/Wolfgangrush/indian-ip-drafting) | Copyright · Trade Marks · Patents · Designs + HC IP Divisions (post-IPAB-abolition) + Anton Piller / John Doe |

Each plugin can be installed independently, each plugin's Rule 36 firewall is narrow and reviewable, each plugin's bench / forum discipline is depth-validated within its scope, and the user installs only what they need.

---

## Why this exists

Indian property practice currently has no open-source conveyancing-instrument-drafting infrastructure. The conveyancing register is centuries-old (English Conveyancing Act 1881 influenced our drafting style), the State Stamp Act schedules vary widely, the Ready Reckoner / Circle Rate / Guidance Value frameworks differ State-by-State, the *Suraj Lamp* (2012) discipline is widely under-enforced in practice (with GPA-Sale combinations still attempted by under-trained practitioners), and the personal-law overlays add depth that no foreign tool can address.

This plugin codifies the universal conveyancing skeleton, the State-Stamp-Act framework, the *Suraj Lamp* discipline, the *Kale* family-settlement framework, the Indian Trusts Act three-certainties rule, the Wakf Act perpetuity-in-ultimate-purpose discipline, the Section 7 ISA partition rule, the personal-law overlays, and the title-chain methodology — into machine-readable form.

Foreign legal-AI tools cannot fill this gap. The procedural conventions are jurisdiction-specific; the conveyancing register is Indian-English-distinct; the State Stamp Acts are unique-per-State; the personal-law overlays are unique to Indian conveyancing.

---

## Roadmap

- [x] **v0.1.0-alpha (current)** — universal conveyancing skeleton + 10 instrument-type skills + 6-agent pipeline + privacy firewall + Verifier disciplines + 8 State exemplars (Maharashtra · Karnataka · Tamil Nadu · Delhi · UP · Gujarat · West Bengal · Telangana)
- [ ] **v0.1.x** — bug fixes, register polish, formatting refinements; remaining 8+ State exemplars (Andhra Pradesh · Kerala · Rajasthan · MP · Odisha · Punjab · Haryana · Bihar · the North-Eastern States · Goa)
- [ ] **v0.x onward** — additional instrument-type skills (Specific Performance Plaint · Cancellation of Instrument Plaint · Possession Suit · Adverse Possession Defence · Lis Pendens Notice · Lien Notice · Public Charitable Trust under State Public Trusts Acts) ; deeper RERA-overlay for under-construction projects; deeper personal-law nuances (Christian Wills + Parsi Chapter III-A + Muslim Hiba sub-school differences)
- [ ] **v1.0.0** — stable release after community-validated formatting and field-testing

---

## Contributing

Advocates with regular conveyancing / estate-drafting / property-litigation practice are invited to contribute state-config calibration. Open a GitHub issue with: practice State + applicable State Stamp Act + key Articles + Ready Reckoner framework + Sub-Registrar circles + applicable State Land Reforms / Apartment Ownership / RERA / Co-op Societies overlays.

Pull requests welcome with one-paragraph explanation + State Act / Rule reference.

This plugin is open source under MIT.

---

## Contact

Author and maintainer: **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa.

GitHub: <https://github.com/Wolfgangrush>

---

## Author and brand

The author is **Rushikesh R. Mahajan**, Advocate, practising before the Bombay High Court, Nagpur Bench. The plugin is published under the open-source brand **Wolfgang Rush**, which is the author's publishing handle for legal-technology infrastructure. Personal accountability under the Advocates Act 1961 attaches to the author regardless of the use of a publishing handle.

---

## Provenance and privilege statement

See `NOTICE.md` for the full provenance + privilege + privacy + Rule 36 compliance statement. The short version:

- The plugin contains only universal procedural skeletons, formatting conventions, statutory references, and generic placeholders
- The plugin contains no specific client matter, no client communications, no client documents, no personal data of any data principal, and no tracking / telemetry / analytics
- The plugin is, in legal character, identical to a published conveyancing textbook — procedural knowledge in machine-readable form
- The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961 and the Bar Council of India Rules

---

## Compliance posture — Supreme Court e-Committee AI framework

This plugin is **assistive drafting infrastructure**, not autonomous decision-making software. Its operational posture is aligned with the Supreme Court of India e-Committee's stated position on AI in legal work.

> *"AI and digital tools must be used as supportive instruments and should not be allowed to override judicial reasoning."*
>
> — **Justice Rajesh Bindal**, Judge, Supreme Court of India
> [*Judicial Process Re-engineering and Digital Transformation*](https://www.sci.gov.in/press-release-dated-april-12-2026/) conference, 11–12 April 2026
> Organised by the Supreme Court e-Committee in collaboration with the Department of Justice, Government of India.
> ([Coverage — Law Trend](https://lawtrend.in/ai-must-not-replace-judicial-reasoning-warns-supreme-court-justice-rajesh-bindal/))

The same posture underpins the Supreme Court's own AI infrastructure for the judiciary:

- **[SUPACE](https://www.drishtiias.com/daily-news-analysis/ai-portal-supace)** — *Supreme Court Portal for Assistance in Court Efficiency.* AI-enabled assistive tool launched on 6 April 2021 by then-CJI S.A. Bobde. Provides legal research, fact extraction, document review, and drafting assistance to judges and legal researchers. **By design, SUPACE is not a decision-making system** — it processes facts and surfaces them to the human user. The Supreme Court has recommended adoption across all Indian High Courts.

- **[SUVAS](https://www.drishtijudiciary.com/current-affairs/supreme-court-vidhik-anuvaad-software-suvas)** — *Supreme Court Vidhik Anuvaad Software.* AI-powered translation tool launched in November 2019 by then-CJI S.A. Bobde. Translates judicial documents, orders, and judgments between English and ten Indian regional languages.

### What this plugin does — and does not — do under that framework

**Does:**

- Generate structural skeletons of pleadings, drawing on public statutes, schedule forms, and court rules.
- Run a six-agent assistive pipeline (Reader → Formatter → Drafter → Verifier → Refiner → Overseer) over the user's case facts.
- Surface citations, procedural anchors, and bench-specific conventions for advocate review.

**Does NOT:**

- Generate final filings autonomously.
- Substitute for advocate professional judgment.
- Replace human verification.
- Operate without an enrolled advocate retaining full professional responsibility.

**Every draft produced through this plugin must be advocate-owned and human-verified before filing.** The enrolled advocate using this plugin retains full professional responsibility under the Advocates Act 1961 and the Bar Council of India Rules, including verification of facts, accuracy of citations, correctness of legal grounds, propriety of the prayer, and signature on every pleading filed.

This is the same standard the Supreme Court itself applies to its own AI infrastructure (SUPACE / SUVAS): **AI as supportive instrument, never as decision-maker.**

---

## Disclaimer and Bar Council of India Rule 36 compliance

This repository is published as a personal open-source contribution to the legal-technology ecosystem. It is **not** an advertisement of professional services, **not** a solicitation of work, **not** an undertaking to act as counsel in any matter, and **not** a vehicle through which the author accepts professional engagement.

Bar Council of India Rule 36 of the Standards of Professional Conduct and Etiquette prohibits an advocate from soliciting work or advertising professional services through any medium. This repository complies with Rule 36 in both letter and spirit.

The plugin is published in the same legal character as any practitioner's open-source library, public continuing-legal-education contribution, or published textbook chapter — the medium is software, the content is procedural knowledge, the practitioner retains full Bar discipline and accountability.

---

## License

MIT — see `LICENSE`.
