---
name: title-investigation-report-draft
description: Draft a Title Investigation Report (Title Search Memorandum / Marketable Title Opinion / Title Due-Diligence Report) — produced for a purchaser / mortgagee / financier before completing a transaction on immovable property. NOT a registered instrument; produced as a formal legal opinion document. Encodes the title-chain-back-to-30-years discipline, the encumbrance-certificate analysis from the Sub-Registrar's office, the mutation-entry / revenue-record cross-check, the lis-pendens / litigation / charge / attachment search, and the marketable-title opinion with risk-flag listing. Auto-fires on "draft title investigation report", "draft title search memorandum", "draft title opinion", "draft due-diligence title report", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Title Investigation Report Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md` (with adaptations — a Title Investigation Report is a legal opinion document, not a conveyancing instrument; the Title / Parties block / Recitals / Witnesses / Signatures sections are replaced by the legal-opinion structure of an Engagement Letter + Methodology + Findings + Opinion + Risk Flags + Reservations)
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Report metadata

```yaml
report_type_line: TITLE INVESTIGATION REPORT
report_short_code: TIR
role_party_1: Reporting Advocate (the legal opinion is the advocate's professional output)
role_party_2: Instructing Client (purchaser / mortgagee / financier / counter-party seeking the title opinion)
role_party_3: Reported Owner (the current vendor / mortgagor whose title is being investigated)
typical_consideration: professional fee charged by Reporting Advocate to Instructing Client
report_structure:
  - "1. Engagement details — Instructing Client, scope of engagement, date of instruction, date of report, fee basis"
  - "2. Property description — full Schedule of Property under investigation"
  - "3. Documents examined — title chain documents furnished + documents obtained from Sub-Registrar / revenue authorities + documents inspected on site"
  - "4. Methodology — searches conducted, period covered, sources examined"
  - "5. Title chain — chronological narrative from earliest available document (or 30 years back) to current ownership"
  - "6. Encumbrance analysis — encumbrance certificate findings + verification of disclosed encumbrances"
  - "7. Mutation entries — revenue records / society records / corporation records cross-check"
  - "8. Litigation search — court records search (district court / High Court / Tribunals / NCLT / DRT) for pending / disposed-of litigation"
  - "9. Statutory dues — property tax / municipal dues / society dues / electricity / water dues clearance"
  - "10. RERA compliance — for RERA-registered projects under construction"
  - "11. Apartment Ownership / Co-operative Housing Society compliance — flat / society NOC"
  - "12. Opinion — marketable title YES / NO / WITH RESERVATIONS"
  - "13. Risk flags — material risks identified, with severity classification"
  - "14. Reservations — limitations of the opinion, documents not examined, assumptions made"
  - "15. Signature block — Reporting Advocate, Bar Council enrolment number, date, place"
```

## Title-chain discipline (30 years standard)

The title chain is traced back to:

- (a) the EARLIEST mother deed available — typically the original Sale / Gift / Partition that established the chain — OR
- (b) at least 30 years from the date of the report, where the property has been with the same family for over 30 years (presumption of good title under Article 65 Limitation Act 1963 read with the doctrine of adverse possession favouring the long-standing possessor)

The title-chain narrative establishes:

- Each successive ownership transfer (Sale / Gift / Partition / Will / Inheritance / Settlement)
- Each transfer's date, parties, instrument type, registration number, and Sub-Registrar office
- Any link in the chain that is doubtful, missing, or potentially defective is FLAGGED

## Encumbrance certificate analysis

The encumbrance certificate (EC) is obtained from the Sub-Registrar's office. Standard practice:

- **13-year EC** is the minimum standard for residential / smaller transactions
- **30-year EC** is the preferred standard for larger / commercial transactions and for mortgages
- The EC must cover ALL encumbrances — mortgages, leases of long term, family settlements, partition decrees, attachments, lis pendens, charges by Banks / NBFCs / Tribunals

Any encumbrance found in the EC is cross-checked against:

- The vendor's disclosure
- The mortgagor's covenants
- Any subsisting orders (Sub-Registrar's records / e-courts / Stamp Authority)

## Mutation entries / revenue records cross-check

- For agricultural land: 7/12 extract / Form VI-XII / Khasra-Khatauni / Patwari records
- For urban property: Municipal records / Property Tax records / Society Allotment register
- For flats in Co-operative Housing Society: Society Share Certificate + Allotment Letter + Society NOC for transfer
- For company-owned property: RoC charge search (Form CHG-1, CHG-4)

## Litigation search

Searches conducted:

- District Court e-courts portal (https://services.ecourts.gov.in) — for pending / disposed civil and criminal cases
- High Court website — for pending / disposed proceedings + writ petitions involving the property / vendor
- NCLT website — for CIRP / liquidation orders against the vendor (corporate)
- DRT website — for debt-recovery orders / SARFAESI attachments
- Section 173 attachment register at the Sub-Registrar
- CIBIL / credit-bureau searches (where the vendor's financial standing is relevant)

## Statutory dues clearance

Pre-transaction clearance verification:

- Property Tax: latest receipt + arrears statement
- Municipal Dues: water tax / sewage / building tax
- Society Dues: maintenance / corpus / sinking fund dues (with NOC from Society for transfer)
- Electricity: latest bill + clearance
- Water: latest bill + clearance
- For commercial property: Trade Licence dues / Profession Tax dues (where applicable)

## RERA compliance (for under-construction projects)

Where the property is a flat / villa in a RERA-registered project:

- RERA project registration number and date
- Carpet area as defined under RERA
- Possession date as per RERA registration
- Promoter compliance with disclosed schedule
- Buyer's protection under Section 18 RERA in the event of delay
- Buyer's right to claim refund / compensation

## Marketable title opinion

The opinion is one of three classifications:

- **MARKETABLE TITLE — UNQUALIFIED** — no defects, no encumbrances, no pending litigation, clean chain
- **MARKETABLE TITLE — WITH RESERVATIONS** — minor defects / curable encumbrances / acceptable risks; client may proceed with documented protection
- **NOT MARKETABLE TITLE** — material defects / uncurable encumbrances / serious litigation; client should NOT proceed without further investigation / cure

## Risk flags

Each identified risk is classified:

- **CRITICAL** — would render the title not marketable (e.g. unauthorised construction without building permit; subsisting mortgage; pending partition suit)
- **MATERIAL** — significantly affects the value or use (e.g. unpaid property tax; flat in a building with society NOC pending)
- **MINOR** — readily curable / immaterial (e.g. mutation entry not yet effected; minor description discrepancy)

## Reservations

Standard reservations:

- The opinion is based on documents furnished and searches conducted within the time and scope of the engagement
- The opinion does not cover off-record claims (e.g. adverse possession claims by third-party occupants not in the records; oral wakf / private trust claims)
- The opinion does not cover unrevealed government acquisition proceedings (CSEZ / land acquisition by State / NHAI / Railway / etc.)
- The opinion is valid as of the date of the report; subsequent events may affect title
- The Reporting Advocate's liability is limited to professional negligence and is subject to the engagement terms

## No registration / no stamp

A Title Investigation Report is a LEGAL OPINION document, not a conveyancing instrument. It does NOT require:

- Registration under the Registration Act 1908
- Stamp under the Indian Stamp Act 1899 / State Stamp Act

It is signed by the Reporting Advocate and delivered to the Instructing Client as part of the professional engagement.

## Common challenges / issues per Overseer agent

1. **Insufficient title chain** — chain less than 13 years OR missing mother-deed link → risk flag
2. **EC period inadequate** — less than 13-30 years covered → risk flag
3. **Lis pendens not searched** — counter by explicit search confirmation
4. **RERA non-compliance** — for projects under construction → critical risk flag
5. **Society NOC pending** — for flats → material risk flag
6. **Encumbrance disclosed but not searched in EC** — verify via Sub-Registrar fresh EC

## Cross-reference

- For Sale Deed → use `indian-contracts-drafting/sale-deed-draft`
- For Mortgage Deed (post-investigation) → use `mortgage-deed-draft` in this plugin
- For Gift Deed → use `gift-deed-draft` in this plugin
