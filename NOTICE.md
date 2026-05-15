# NOTICE — Provenance and Privilege Statement

This document is part of the public release of the `indian-property-drafting` plugin (v0.1.0-alpha and onwards). It declares the provenance of the plugin's content, in order to address any question about advocate-client privilege, client confidentiality, professional ethics, personal-data protection, commercial confidentiality, and Sub-Registrar / Stamp Authority recognition that may be raised by any reader, complainant, regulator, or Bar Council disciplinary authority.

The plugin is **deed-config-aware** and **state-config-aware**: the universal structural skeleton of any Indian property / conveyancing / estate instrument is uniform, and the parties' chosen State Stamp Act schedule, Sub-Registrar circle, Ready Reckoner / Market Value rate, applicable family-member concessional rate, applicable State Wakf Board / Charity Commissioner reference, and applicable mutation framework are supplied by the user via a `deed-config.md` file in the deal folder.

This NOTICE is published in plain language so that any reader — practising advocate, judge, Sub-Registrar, Stamp Authority officer, Charity Commissioner, Wakf Board officer, Bar Council officer, regulator, member of the public, fellow developer — can understand the position without ambiguity.

---

## 1. What this plugin contains

This plugin contains the following categories of content, and **only** the following categories of content:

(a) **Universal property / conveyancing / estate instrument skeleton** — the structural shape of any Indian property / conveyancing / inter-vivos transfer / estate instrument (Title, Parties block, Recitals with title-chain narrative, Operative clauses, Schedule of Property, Encumbrance / Title warranties, Stamping note, Registration note, Witnesses, Signatures).

(b) **Formatting conventions** — text-formatting conventions for Indian property instruments (title in title case; defined terms in bold on first use; numbered clauses with sub-paragraphs; Schedule of Property with municipal / survey / Ready Reckoner reference; signature block with witness clauses where statute requires under Section 123 TPA / Section 68 IEA / Section 63 ISA).

(c) **Statutory references** — citations to public statutes (Indian Contract Act 1872, Transfer of Property Act 1882, Registration Act 1908, Indian Stamp Act 1899 + applicable State Stamp Acts, Indian Easements Act 1882, Indian Trusts Act 1882, Wakf Act 1995, Mussalman Wakf Validating Act 1913, Mussalman Personal Law (Shariat) Application Act 1937, Hindu Succession Act 1956, Indian Succession Act 1925, Hindu Marriage Act 1955, Special Marriage Act 1954, Powers of Attorney Act 1882, Bharatiya Sakshya Adhiniyam 2023, Specific Relief Act 1963, Limitation Act 1963, Code of Civil Procedure 1908 — Order 21 Rule 90 / Section 47 execution-side; Real Estate (Regulation and Development) Act 2016 where applicable; Land Revenue Codes of the various States; State-specific Apartment Ownership Acts; the State Co-operative Societies Acts).

(d) **Procedural rule references** — citations to public rules (Registration Act Rules / Sub-Registrar instructions, the various State Stamp Act Schedules, the various State Ready Reckoner / Annual Statement of Rates / Circle Rate / Guidance Value / Market Value notifications, Wakf Act Regulations, Charity Commissioner Rules, State Land Records / Revenue Records Manuals, applicable State Apartment Ownership / Co-operative Housing Society Rules).

(e) **Generic placeholders** — every variable in every template is a placeholder (`[Donor]`, `[Donee]`, `[Settlor]`, `[Trustee]`, `[Beneficiary]`, `[Wakif]`, `[Mutawalli]`, `[Mortgagor]`, `[Mortgagee]`, `[Releasor]`, `[Releasee]`, `[Co-owner-1]`, `[Co-owner-2]`, `[Schedule of Property]`, `[Consideration]`, `[Ready Reckoner Value]`, `[Sub-Registrar Office]`, `[Survey No.]`, `[Municipal No.]`, `[Mutation Entry No.]`). No placeholder is filled with any specific transaction, party, consideration figure, property description, registration number, or identifying information.

(f) **Anti-hallucination and privacy-firewall workflow** — six agents (Reader, Format, Drafter, Verifier, Refiner, Overseer) that operate on a deal folder supplied by the user. The plugin itself contains no deal folder. The Reader substitutes every party name, every property description, every consideration figure, every Survey / Municipal number, and every Sub-Registrar registration reference with placeholders before downstream AI processing.

---

## 2. What this plugin does NOT contain

This plugin does **not** contain any of the following, and has never contained any of the following at any point in any committed version:

(a) **No specific client matter or transaction.** No client of the author, and no specific conveyancing transaction or property dispute handled by the author or any client, appears in the plugin — by name, by Survey number, by Municipal number, by Sub-Registrar registration reference, by consideration figure, by property description, by Ready Reckoner value, by PAN / Aadhaar, by family-tree, by mutation entry, or by any other identifying signature.

(b) **No client communications.** No oral or written communication made to the author by or on behalf of any client (whether a buyer, seller, donor, donee, mortgagor, mortgagee, settlor, trustee, beneficiary, wakif, mutawalli, co-owner, releasor, releasee, or any other party) appears in the plugin in any form.

(c) **No client documents.** No document or instrument with which the author has become acquainted in the course of professional employment as an advocate appears in the plugin, in original, in redacted, in summary, in extract, or in pattern. This includes — but is not limited to — sale deeds, gift deeds, exchange deeds, release deeds, trust deeds, wakf deeds, easement deeds, partition deeds, settlement deeds, mortgage deeds, title chains, encumbrance certificates, mutation entries, family trees, and any State Wakf Board / Charity Commissioner filings of any specific party.

(d) **No personal data of any data principal.** The plugin processes no personal data, collects no personal data, stores no personal data.

(e) **No specific Schedule of Property, no specific Ready Reckoner value, no specific Sub-Registrar registration reference, no specific Mutation Entry** of any specific transaction.

(f) **No client list, no chamber list, no associate list, no opposing-counsel list, no Sub-Registrar-specific intelligence, no Charity-Commissioner-specific intelligence.**

(g) **No tracking, no telemetry, no analytics, no opt-in error reporting, no login, no account, no cloud sync.** The plugin runs entirely on the user's machine. The author receives no information about who installs the plugin, who uses it, on what transactions, with what consideration, with what outcomes.

---

## 3. The legal distinction

Indian law has long recognised a clear distinction between two categories:

(i) **Specific client communications and documents** — protected under Section 132 of the Bharatiya Sakshya Adhiniyam 2023 (formerly Section 126 of the Indian Evidence Act 1872) and under Rule 17 of the Bar Council of India Standards of Professional Conduct and Etiquette. This category is privileged and confidential.

(ii) **General professional knowledge of property law, conveyancing practice, and estate / trust / wakf instrument drafting** — an advocate's accumulated knowledge of how a Gift Deed is structured under Sections 122-129 TPA 1882, what the Section 17 Registration Act requires for any non-testamentary instrument creating, declaring, assigning, limiting, or extinguishing any right, title or interest in immovable property of value ₹100 or more, what the *Suraj Lamp & Industries v. State of Haryana* (2012) 1 SCC 656 discipline mandates about GPA-Sale not being a valid mode of title transfer, what the Section 17(1A) read with Section 53A TPA 1882 require about agreements-to-sell post the 2001 amendment, what the *Kale v. Deputy Director of Consolidation* (1976) 3 SCC 119 framework establishes for Family Settlement Deeds, what the Indian Trusts Act 1882 Sections 14-30 prescribe for private trusts, what the Wakf Act 1995 prescribes about Wakf Board registration, and the State-specific Stamp Act schedules for each instrument-type / consideration-bracket. This category is the advocate's own professional knowledge. It is not the property of any specific client. It is not privileged.

This plugin operates **entirely within category (ii)**.

Every Indian advocate accumulates this knowledge through years of practice, through study of Mulla on the Transfer of Property Act, B.B. Mitra on the Registration Act, the Indian Stamp Act commentaries, Mulla on Hindu Law / Muslim Law, Madhavan Pillai on Trusts, the Mussalman Wakf textbooks, the State Land Records Manuals, the Sub-Registrar's Manual, and the case-law of the Supreme Court and the High Courts on conveyancing, partition, settlement, trust formation, wakf creation, and easement disputes. The plugin codifies that accumulated procedural knowledge into machine-readable form. It does not codify any client's confidential information.

The plugin is, in this respect, identical in legal character to a published conveyancing textbook, a continuing legal education handout, or a senior advocate's drafting-style lecture. The medium is software. The content is procedural knowledge.

---

## 4. The author's professional position

The author is **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa, practising before the Bombay High Court, Nagpur Bench. The plugin is published under the open-source brand **Wolfgang Rush**, which is the author's publishing handle for legal-technology infrastructure; the real-identity accountability declared in this section attaches to the author personally and is not displaced by the use of a publishing handle.

The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961, the Bar Council of India Rules, and the Standards of Professional Conduct and Etiquette.

The plugin is published as a personal contribution to the open-source legal-technology ecosystem. It is published without any commercial channel, without any solicitation of professional work, without any advertisement of professional services, and without any acceptance of work through this repository.

This NOTICE is filed of record in this open-source repository so that any person who reads, reviews, audits, or assesses this plugin has full transparency about its provenance and its scope from the moment of release.

---

## 5. Verification of clean provenance

The repository owner shall maintain, on a private offline record, a build log demonstrating that every line of every file in the plugin was either:

(a) authored from scratch as procedural skeleton, OR
(b) derived from public statute, public rule, public judgment, or public conveyancing textbook, OR
(c) derived from the author's own original procedural knowledge as a practitioner.

No line of any file was, at any stage, copied from, paraphrased from, summarised from, or pattern-matched against any specific client matter, transaction, client communication, or client document.

This NOTICE is the author's signed declaration of that position.

---

## 6. Reporting concerns

If any reader, regulator, fellow advocate, Sub-Registrar, or member of the public believes any specific content in this plugin is derived from a specific client matter or specific confidential communication, the reader is requested to:

(a) identify the file and line at issue in the plugin,
(b) identify the specific client matter or communication believed to be the source,
(c) explain the basis of the belief,

and raise the concern via a GitHub Issue on this repository.

Concerns raised with these particulars will be investigated and the file or line will be removed or rewritten if the concern is well-founded. Concerns raised without these particulars cannot be acted upon.

---

## 7. Standing instruction to forks and derivatives

Any fork, derivative, downstream redistribution, or commercial integration of this plugin or its content shall preserve this NOTICE in unmodified form, and shall extend the same provenance discipline to any content added in the fork or derivative.

This NOTICE travels with the code under the same MIT licence that governs the source.

---

*Signed and dated by way of public commit history on the repository. The author stands by every line of this notice.*
