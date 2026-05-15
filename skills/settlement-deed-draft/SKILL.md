---
name: settlement-deed-draft
description: Draft a Family Settlement Deed under the framework of Kale v. Deputy Director of Consolidation (1976) 3 SCC 119 — a bona-fide family arrangement reached among family members to settle existing / future disputes, by mutual relinquishment of contesting claims, recognising existing rights rather than creating new ones. Compulsorily registrable under Section 17(1)(b) Registration Act 1908. Encodes the Kale-framework five ingredients (bona-fide arrangement / mutual relinquishment / antecedent claims / no requirement to prove antecedent title / public-document recognition where registered), the family-settlement vs partition vs gift demarcation, and the Article 58 (or equivalent) concessional stamp-duty rates available in most States for family settlements. Auto-fires on "draft family settlement", "draft settlement deed", "draft family arrangement", "Kale settlement", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Family Settlement Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: FAMILY SETTLEMENT DEED
instrument_short_code: SETTLEMENT_DEED
role_party_1: Family Member - 1
role_party_N: Family Member - N (all relevant family members with contesting / antecedent claims)
typical_consideration: nil (mutual relinquishment + restoration of family harmony — Kale framework)
operative_clauses:
  - "Recital of family relationship — *'WHEREAS the Parties hereto are members of the same family, related as [list relationships — father / mother / sons / daughters / siblings / spouses / grandchildren / etc.] as more particularly described in the family tree at Annexure A hereto.'*"
  - "Recital of antecedent claims / disputes — *'AND WHEREAS certain disputes / claims / counter-claims have arisen amongst the Parties in respect of the family property / family business / family entitlements as described in the Schedule hereto, including [precise description of contesting claims — inheritance dispute / share-allocation dispute / family-business profit-sharing / contesting partition / will validity / etc.].'*"
  - "Recital of family arrangement — *'AND WHEREAS the Parties, with a view to settling all such disputes amicably and to restoring family harmony and peace, and after due deliberation amongst themselves with the assistance of family elders / mediators / legal counsel, have arrived at the family arrangement set out herein.'*"
  - "Recital of Kale framework — *'AND WHEREAS this family arrangement is made in good faith, in the spirit of compromise, with mutual relinquishment of contesting claims, and is intended to recognise the existing rights of each Party rather than to create new rights — in conformity with the framework laid down in Kale v. Deputy Director of Consolidation (1976) 3 SCC 119 and the lineage of Supreme Court precedent thereafter.'*"
  - "Settlement terms — *'NOW THIS DEED WITNESSETH THAT in pursuance of the said family arrangement and in consideration of mutual relinquishment of contesting claims by the Parties hereto, IT IS HEREBY DECLARED, AGREED, AND SETTLED as follows: (a) the property / asset / right described in Schedule-X1 is recognised as belonging to [Family Member-1] absolutely; (b) the property / asset / right described in Schedule-X2 is recognised as belonging to [Family Member-2] absolutely; (c) [further allotments / recognitions for each Family Member]; (d) all contesting claims of every Party against every other Party in respect of the said properties / assets / rights are hereby waived, withdrawn, and forever quitclaimed.'*"
  - "Restoration of family harmony — *'The Parties confirm that this settlement is reached freely, voluntarily, after due consideration, and with the intent to settle ALL disputes amongst them in respect of the family property and family business, without any reservation. The Parties undertake to live in peace and harmony as members of a family and to refrain from raking up any old or settled grievances.'*"
  - "Mutation and recognition — *'The Parties undertake to apply for mutation of the recognised rights in the revenue records / society records / municipal records / company records (where applicable) as expeditiously as possible after registration of this Deed.'*"
  - "No third-party claim — *'The Parties confirm that no third party (whether family member or not) has any contesting claim in respect of the said properties; if any such third-party claim is raised in future, the Parties shall jointly defend the recognised rights and shall indemnify each other against costs of defence.'*"
  - "Indemnity — *'Each Party undertakes to indemnify the other Parties against any future claim, demand, action, or proceeding from his / her heirs, legal representatives, or successors in respect of the rights recognised herein.'*"
stamp_position: "Article 58 of the applicable State Stamp Act Schedule (Family Settlement) — significantly concessional vs Gift / Sale rates. Maharashtra: ₹200 to ₹500 nominal for family settlement among blood-relatives (verify current notification). Karnataka, Tamil Nadu, Delhi, Gujarat have similar concessional rates — see State exemplar."
registration_position: "COMPULSORILY REGISTRABLE under Section 17(1)(b) Registration Act 1908 where the settlement affects immovable property rights of value ₹100 or more. Registration before the Sub-Registrar of the area where the immovable property is situated within FOUR MONTHS of execution under Section 23 Registration Act 1908. UN-REGISTERED Family Settlement Deeds — under Kale (1976) — are receivable as evidence of the family arrangement and as collateral evidence of severance of joint status, but do NOT confer title that is registrable on revenue records."
witness_requirement: "ONE witness is sufficient; TWO witnesses are routinely taken for evidentiary safety + family-elder / mediator signature as recitation of bona fides."
```

## Kale framework — the five ingredients

*Kale v. Deputy Director of Consolidation* (1976) 3 SCC 119 lays down five ingredients for a valid Family Settlement:

1. **Bona-fide family arrangement** — entered into freely and voluntarily, in good faith, to settle bona-fide disputes within the family
2. **Mutual relinquishment of contesting claims** — each Party gives up his / her contesting claim against the others
3. **Antecedent claims / disputes** — the settlement is in respect of pre-existing claims; it is not a transfer / conveyance of rights NOT antecedently held
4. **No requirement to prove antecedent title** — the Parties need NOT prove that the relinquished claims were good-in-law; the bona-fide assertion of the claim is sufficient
5. **Family harmony restoration** — the underlying purpose is to restore peace and harmony within the family

A settlement satisfying these five ingredients is recognised as a valid Family Settlement Deed, with concessional stamp duty + public-document recognition.

## Family Settlement vs Partition vs Gift — demarcation

| Feature | Family Settlement | Partition | Gift |
|---|---|---|---|
| Pre-existing antecedent claim | YES (asserted; need not be proved) | YES (definite legal share) | NO (Donor has full title; Donee has no antecedent claim) |
| Mutual relinquishment | YES (each Party gives up contesting claim) | YES (each Party relinquishes share in others' allotted portions) | NO (one-way transfer) |
| Bona-fide family disputes | YES (existing or future) | Not necessarily | Not relevant |
| Stamp rate | Article 58 concessional | Section 7 highest-share-aggregate concessional | Article 34 (concessional for family) |
| Witnesses | One sufficient (two preferred) | One sufficient | TWO MANDATORY (Section 123 TPA) |
| Recognition | Public document on registration (Kale) | Public document on registration | Public document on registration |

The critical distinction is the **antecedent claim**: a Family Settlement settles a CONTEST among family members, whereas a Partition divides DEFINITE LEGAL SHARES, and a Gift transfers ownership where the Donee has NO antecedent claim.

## Common challenges to a Family Settlement Deed (per Overseer agent)

1. **Antecedent claim not pleaded** — Sub-Registrar / opposing party will challenge the instrument as not really a Family Settlement; counter by precise pleading of the disputed claims
2. **Bona-fide test failure** — opposing party will allege the settlement was reached under coercion / fraud / undue influence; counter by recital of family-elder facilitation + independent legal advice + free consent
3. **Disguised Sale / Gift to evade stamp** — Sub-Registrar may refer to Collector under Section 47A Indian Stamp Act 1899 where the consideration is disproportionate or where one Party receives a windfall; counter by genuine-family-dispute recital
4. **Missing family members** — opposing family member (especially post-2005 Hindu daughter coparcener) will challenge the settlement as void for non-joinder; counter by full family tree + signatures
5. **Future disputes excluded** — opposing party may later raise a claim not covered by the settlement; counter by comprehensive-coverage clause + future-claim-waiver

## Cross-reference

- For full Partition with definite legal shares → use `partition-deed-draft` in this plugin
- For one-way Gift → use `gift-deed-draft` in this plugin
- For Release of share by one Party to another (post-partition) → use `release-deed-draft` in this plugin
- For Will → use `indian-contracts-drafting/will-draft`
