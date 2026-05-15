---
name: mortgage-deed-draft
description: Draft a registered Mortgage Deed under Section 59 read with Section 58 of the Transfer of Property Act 1882. Encodes the six TPA mortgage types (simple mortgage / mortgage by conditional sale / usufructuary mortgage / English mortgage / equitable mortgage by deposit of title deeds / anomalous mortgage), the Section 60 TPA right of redemption (cannot be clogged — Murarilal v. Devkaran framework), the Section 67 TPA right of foreclosure / sale on default, the registration discipline under Section 59 TPA (registered instrument + two attesting witnesses), and the Stamp Act ad-valorem framework on the secured amount. This is the drafting-side mortgage instrument — for mortgage SUITS (Order 34 CPC / DRT OA for banking mortgages), use indian-banking-drafting. Auto-fires on "draft mortgage deed", "draft registered mortgage", "draft TPA mortgage", "draft equitable mortgage", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Mortgage Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: MORTGAGE DEED
instrument_short_code: MORTGAGE_DEED
role_party_1: Mortgagor
role_party_2: Mortgagee
typical_consideration: secured loan amount / advance
operative_clauses:
  - "Recital of debt / loan — *'WHEREAS the Mortgagor has obtained / hereby obtains from the Mortgagee a loan / advance of ₹ ___ (Rupees ___ only) (hereinafter the 'Secured Amount'), repayable on the terms set out in [the Loan Agreement dated ____ at Annexure A / herein].'*"
  - "Identification of mortgage type — *'NOW THIS DEED WITNESSETH THAT for securing the Secured Amount together with interest at ___% per annum / [agreed rate] from the date of disbursement, the Mortgagor hereby creates a [SIMPLE MORTGAGE / MORTGAGE BY CONDITIONAL SALE / USUFRUCTUARY MORTGAGE / ENGLISH MORTGAGE / EQUITABLE MORTGAGE BY DEPOSIT OF TITLE DEEDS / ANOMALOUS MORTGAGE] over the property described in the Schedule hereto (hereinafter the 'Mortgaged Property') in favour of the Mortgagee, on the terms set out herein.'*"
  - "[For Simple Mortgage] — *'The Mortgagor undertakes personally to repay the Secured Amount and agrees that, in the event of default, the Mortgagee shall be entitled to cause the Mortgaged Property to be sold and the sale proceeds applied towards satisfaction of the Secured Amount, with the Mortgagor remaining personally liable for any shortfall.'*"
  - "[For Mortgage by Conditional Sale] — *'The Mortgagor ostensibly sells the Mortgaged Property to the Mortgagee, on the express condition that (a) on default in payment of the Secured Amount within ___ months, the sale shall become absolute; OR (b) on payment of the Secured Amount within ___ months, the sale shall become void and the Mortgaged Property shall stand re-transferred to the Mortgagor. The Parties acknowledge that this is a Mortgage by Conditional Sale under Section 58(c) TPA and NOT a Sale; the Mortgagor's right of redemption shall remain available.'*"
  - "[For Usufructuary Mortgage] — *'The Mortgagor delivers possession of the Mortgaged Property to the Mortgagee, who shall be entitled to receive the rents / profits / usufruct of the Mortgaged Property in lieu of interest, in lieu of part-payment, or in lieu of payment of the Secured Amount itself (as agreed). The Mortgagor's right of redemption shall remain available on payment of the Secured Amount.'*"
  - "[For English Mortgage] — *'The Mortgagor transfers the Mortgaged Property absolutely to the Mortgagee, on the express covenant that the Mortgaged Property shall be re-transferred to the Mortgagor on payment of the Secured Amount on or before ____. In the event of default, the Mortgagee shall be entitled, without intervention of the court but subject to the Transfer of Property Act 1882 and any applicable statute, to cause the Mortgaged Property to be sold.'*"
  - "[For Equitable Mortgage by Deposit of Title Deeds] — *'The Mortgagor has, on the date of execution hereof, deposited with the Mortgagee at [Place — typically a notified town under Section 58(f) TPA] the original title deeds described in the Schedule of Documents at Annexure B hereto, with the intent to create an equitable mortgage over the Mortgaged Property for securing the Secured Amount. NO REGISTRATION of this mortgage is required (Section 59 TPA proviso); only the MEMORANDUM recording the deposit attracts stamp under Article 6 Indian Stamp Act 1899 + applicable State amendments.'*"
  - "Mortgagor's covenants — *'The Mortgagor covenants with the Mortgagee that: (a) the Mortgagor has good and marketable title to the Mortgaged Property; (b) the Mortgaged Property is free from all encumbrances save those disclosed at Annexure C; (c) the Mortgagor shall not create any subsequent mortgage / charge / encumbrance over the Mortgaged Property without prior written consent of the Mortgagee; (d) the Mortgagor shall pay all property taxes, municipal dues, society dues, and other periodic charges in respect of the Mortgaged Property; (e) the Mortgagor shall maintain the Mortgaged Property in good repair and condition; (f) the Mortgagor shall keep the Mortgaged Property insured against fire and other perils, with the Mortgagee as loss-payee.'*"
  - "Default and Mortgagee's rights — *'In the event of default by the Mortgagor in payment of any instalment of the Secured Amount or any interest thereon for a period of ___ days, OR in the event of breach of any covenant under this Deed, the Mortgagee shall be entitled to: (a) declare the entire Secured Amount immediately due and payable; (b) exercise the right of foreclosure / sale as available under Section 67 TPA + applicable type-specific provisions; (c) initiate proceedings under the SARFAESI Act 2002 (where applicable to a banking / NBFC Mortgagee under Section 2(1)(m) of the SARFAESI Act); (d) file a mortgage suit under Order 34 CPC for foreclosure / sale; (e) initiate CIRP under Section 7 IBC 2016 against a corporate Mortgagor (financial-creditor route).'*"
  - "Right of redemption preserved — *'NOTHING IN THIS DEED SHALL OPERATE AS A CLOG ON THE MORTGAGOR'S RIGHT OF REDEMPTION UNDER SECTION 60 OF THE TRANSFER OF PROPERTY ACT 1882. The Mortgagor's right to redeem the Mortgaged Property on payment of the Secured Amount together with interest and costs is preserved in its entirety, and any provision of this Deed inconsistent with such right is deemed to that extent void.'*  (NOTE: This clause is MANDATORY — per Murarilal v. Devkaran and lineage of Supreme Court precedent, any clog on redemption is VOID as opposed to public policy.)"
  - "Re-conveyance on redemption — *'On payment of the Secured Amount together with interest and costs, the Mortgagee shall, within 30 days of such payment, execute a Deed of Re-conveyance in favour of the Mortgagor and deliver up all title deeds and documents held in respect of the Mortgaged Property.'*"
stamp_position: "Article 40 of the applicable State Stamp Act Schedule — ad valorem on the Secured Amount (for registered mortgages). For equitable mortgage by deposit of title deeds — Article 6 (Agreement relating to deposit of title deeds) ad valorem on the Secured Amount but typically at a LOWER rate than Article 40. Verify State exemplar."
registration_position: "COMPULSORILY REGISTRABLE under Section 59 TPA 1882 + Section 17(1)(b) Registration Act 1908 for all registered mortgage types (simple / conditional sale / usufructuary / English / anomalous). EXCEPTION: equitable mortgage by deposit of title deeds is NOT compulsorily registrable (Section 59 TPA proviso); only the Memorandum recording the deposit is stamped. Registration before the Sub-Registrar of the area where the Mortgaged Property is situated within FOUR MONTHS of execution under Section 23 Registration Act 1908."
witness_requirement: "TWO attesting witnesses are MANDATORY under Section 59 TPA 1882 for all registered mortgage types — non-compliance renders the mortgage VOID. For equitable mortgage memorandum: two witnesses recommended though not mandatory."
```

## Section 58 TPA — six mortgage types

- **(a) Simple Mortgage** — personal covenant to pay + right to sell on default; no transfer of possession
- **(b) Mortgage by Conditional Sale** — ostensible sale with condition of re-transfer on payment / absolute sale on default
- **(c) Usufructuary Mortgage** — delivery of possession; Mortgagee receives rents / profits in lieu of interest / Secured Amount
- **(d) English Mortgage** — absolute transfer with covenant of re-transfer on payment by stipulated date
- **(e) Equitable Mortgage by Deposit of Title Deeds** — deposit of title deeds in a notified town with intent to create security; NO registration required
- **(f) Anomalous Mortgage** — any mortgage that is not one of the above five; terms entirely as the contract provides

The Drafter / Verifier confirms one of the six is clearly declared in the operative clause. Ambiguous mortgage type is a ground for the Sub-Registrar to refuse registration.

## Section 60 TPA — right of redemption + clog discipline

The Mortgagor has the **right to redeem** at any time after the Secured Amount becomes due and before the right is foreclosed by court order. The right is INDIVISIBLE from the mortgage and cannot be defeated by:

- **Clogs on redemption** — any term in the mortgage that prevents the Mortgagor from redeeming (e.g. *"unless and until the Mortgagor sells the property to the Mortgagee at a fixed price"*) is VOID
- **Penalty on redemption** — any heavy penalty on exercise of redemption is reducible
- *Murarilal v. Devkaran* and lineage of Supreme Court precedent confirm the absolute discipline

The Drafter expressly preserves the right of redemption in the operative clauses (mandatory clause).

## Section 67 TPA — Mortgagee's right on default

The Mortgagee may:

- (a) Sue for foreclosure (English mortgage, mortgage by conditional sale)
- (b) Sue for sale (simple mortgage, anomalous mortgage)
- (c) Sue on the personal covenant (simple mortgage, English mortgage)
- (d) Exercise out-of-court power of sale (where the mortgage deed confers such power, subject to applicable conditions)

For Bank / NBFC mortgages, SARFAESI Act 2002 provides an additional out-of-court enforcement mechanism (out of scope for the Mortgage Deed itself; relevant to subsequent enforcement proceedings under `indian-banking-drafting`).

## Common challenges to a Mortgage Deed (per Overseer agent)

1. **Mortgage type ambiguous** — Sub-Registrar will refuse registration; counter by clear declaration of one of six TPA types
2. **Clog on redemption** — opposing Mortgagor will challenge the clog; the clog is VOID even if registered; counter by no-clog clause
3. **Two attesting witnesses absent** — Section 59 TPA — mortgage VOID; counter by witness signature recital
4. **Usufructuary mortgage without possession transfer** — counter by simultaneous-possession-transfer clause
5. **Equitable mortgage in non-notified town** — counter by Section 58(f) TPA-notified-town confirmation
6. **Conditional sale dressed as Sale** — opposing Mortgagor will assert it is really a sale (in attempting to redeem); counter by clear mortgage-by-conditional-sale recital
7. **Insurance / preservation default by Mortgagor** — Mortgagee's typical complaint; counter by tight covenant + acceleration clause

## Cross-reference

- For mortgage SUITS (Order 34 CPC) — use `indian-banking-drafting/civil-recovery-suit-draft`
- For SARFAESI enforcement of mortgage (by Bank / NBFC / ARC) — use `indian-banking-drafting/sarfaesi-13-2-notice-draft` and related skills
- For DRT recovery on mortgage (Bank / NBFC ≥ ₹20 lakh claim) — use `indian-banking-drafting/drt-original-application-draft`
- For Sale of property to discharge a mortgage → use `indian-contracts-drafting/sale-deed-draft`
- For Lease (transfer of right of enjoyment for term / rent — distinct from mortgage) → use `indian-contracts-drafting/lease-deed-draft`
