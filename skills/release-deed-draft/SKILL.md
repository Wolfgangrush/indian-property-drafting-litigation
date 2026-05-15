---
name: release-deed-draft
description: Draft a Release Deed for relinquishment of share / right / title / interest in immovable property — typically used (a) between coparceners post-partition to formalise the released share, (b) between joint-tenants where one releases his share to another, (c) where a co-owner relinquishes his right gratuitously or for nominal consideration. Compulsorily registrable under Section 17(1)(b) Registration Act 1908. Encodes the FOR-EVER-QUITCLAIMS-AND-RELEASES conveyancing register, the distinction from Gift / Sale / Settlement, the Section 60 / 62 Indian Stamp Act 1899 release discipline (with State Stamp Act concessional rates for blood-relatives), and the common pattern of Release following a Family Settlement / Partition. Auto-fires on "draft release deed", "draft relinquishment deed", "release of share", "draft quitclaim deed", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Release Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: RELEASE DEED (DEED OF RELINQUISHMENT)
instrument_short_code: RELEASE_DEED
role_party_1: Releasor
role_party_2: Releasee
typical_consideration: nominal / for natural love and affection / for valid consideration depending on the relationship between Parties
operative_clauses:
  - "Recital of joint right — *'WHEREAS the Releasor and the Releasee are jointly entitled to the property described in the Schedule hereto, the Releasor's share being [share-fraction or absolute description] by virtue of [partition / inheritance / joint purchase / family settlement] dated ____ as more particularly described in the Recitals hereto.'*"
  - "Recital of intent to release — *'AND WHEREAS the Releasor desires to relinquish, release, and forever quitclaim all his / her right, title, share, and interest in the said property in favour of the Releasee.'*"
  - "Release granting clause — *'NOW THIS DEED WITNESSETH THAT in consideration of [natural love and affection / a sum of ₹ ___ paid by the Releasee to the Releasor, the receipt of which is hereby acknowledged / mutual release of corresponding rights elsewhere], the Releasor hereby RELEASES, RELINQUISHES, GRANTS, AND FOR EVER QUITCLAIMS unto the Releasee, ABSOLUTELY AND FOREVER, all the right, title, share, and interest of the Releasor in and to the property more particularly described in the Schedule hereto, TO HAVE AND TO HOLD the same as the absolute owner thereof, with all rights, easements, and appurtenances belonging thereto.'*"
  - "Possession — *'The Releasor confirms that the Releasee has been / is forthwith placed in actual / constructive possession of the released share, and the Releasor henceforth has no claim, demand, or interest of any nature in respect of the said property or share.'*"
  - "Indemnity — *'The Releasor undertakes to indemnify and keep indemnified the Releasee against any claim, demand, action, suit, or proceeding from the Releasor or his / her heirs, legal representatives, or successors in respect of the released share.'*"
  - "No further claim — *'The Releasor for himself / herself and his / her heirs, legal representatives, and successors hereby waives, abandons, and gives up any and all rights, claims, and remedies in respect of the released share, and confirms that the Releasee is the absolute and uncontested owner of the said share henceforth.'*"
stamp_position: "Article 55 / 60 of the applicable State Stamp Act Schedule — concessional rates for releases among blood-relatives (typically ₹100-₹500 nominal); ad valorem on the released share's market value where the Parties are not blood-relatives. Maharashtra: ₹200 for blood-relative release; ad valorem otherwise. Verify current notification under State exemplar."
registration_position: "COMPULSORILY REGISTRABLE under Section 17(1)(b) Registration Act 1908 (where the released share is of value ₹100 or more, which it will be for any meaningful Release). Registration before the Sub-Registrar of the area where the property is situated within FOUR MONTHS of execution under Section 23 Registration Act 1908."
witness_requirement: "ONE witness is sufficient (Section 59 TPA + practice); TWO witnesses are routinely taken for evidentiary safety."
```

## Release vs Gift vs Sale — the demarcation

| Feature | Release | Gift | Sale |
|---|---|---|---|
| Parties | Pre-existing joint owners | Donor (sole owner) + Donee | Seller + Buyer |
| Pre-existing right | YES — Releasor must already have a share | NO — Donor's property is being transferred for first time to Donee | NO — Seller transfers his property to Buyer |
| Consideration | Often nominal / for natural love + affection / mutual release | Without consideration | For monetary price |
| Stamp duty | Concessional (most States) | Ad valorem (concessional for family) | Ad valorem (full rate) |
| Registration | Compulsory (Section 17(1)(b)) | Compulsory (Section 17(1)(a)) | Compulsory (Section 17(1)(b)) |
| Witnesses | One sufficient | Two mandatory (Section 123 TPA) | One sufficient |

The crucial distinction is the **pre-existing right**: a Release operates only between Parties who are ALREADY co-owners / coparceners / joint-tenants. If one Party has no pre-existing right, the instrument is a Gift or Sale, not a Release. The Drafter / Verifier confirms the pre-existing-right recital is supported by the title chain.

## Common patterns

1. **Post-partition Release** — coparceners executed a Partition Deed; one coparcener now releases his already-allotted share to another (often a sibling) for natural love and affection — minimal stamp + simple structure
2. **Mother / father releasing inherited share to children** — pre-partition or post-inheritance; concessional stamp
3. **Spouse releasing share in marital home** — typically post-divorce / separation settlement
4. **Co-purchasers' release** — one co-purchaser releases his contributing share to another (typically alongside a refund of contribution)
5. **Sub-purchaser release** — agreement-to-sell rights are released back to original Seller before Sale Deed execution

## Common opposing-counsel challenges to a Release Deed (per Overseer agent)

1. **Pre-existing joint right not established** — opposing party will allege the Releasor had no share; counter by title chain
2. **Stamp duty under-foot** — Sub-Registrar may refer to Collector under Section 47A Indian Stamp Act 1899 for re-assessment where consideration is unrealistic
3. **Disguised Sale** — opposing party will allege Release is really a Sale to evade stamp; counter by family-context + natural-love-and-affection recital
4. **Failure to surrender possession** — opposing party will allege possession not actually transferred; counter by possession-handover clause + acknowledgement by Releasee

## Personal-law overlay

- **Hindu coparcenary** — a coparcener can release his undivided share to other coparceners; the release operates to consolidate the released share in the remaining coparceners (or in the named Releasee within the family)
- **Muslim** — Muslim joint-tenancy in inherited property can be subject to mutual release; concessional stamp typically applies
- **Christian / Parsi** — joint-tenancy and tenancy-in-common under English-law principles via Indian Succession Act 1925

## Cross-reference

- For pure Gift (no pre-existing right) → use `gift-deed-draft` in this plugin
- For Sale (for monetary consideration without pre-existing co-ownership) → use `indian-contracts-drafting/sale-deed-draft`
- For full Partition among co-owners → use `partition-deed-draft` in this plugin
- For family settlement → use `settlement-deed-draft` in this plugin
