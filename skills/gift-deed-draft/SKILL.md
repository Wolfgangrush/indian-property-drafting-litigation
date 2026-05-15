---
name: gift-deed-draft
description: Draft a Gift Deed under Sections 122-129 of the Transfer of Property Act 1882, compulsorily registrable under Section 17(1)(a) of the Registration Act 1908. Encodes the Section 122 ingredients (existing property; voluntary transfer; without consideration; donor competent; donee acceptance during donor's lifetime), the Section 123 TPA execution discipline (registered instrument + two attesting witnesses for immovable property; delivery sufficient for movable property), the Section 126 TPA revocation discipline (gift may be revoked only on grounds specified — happening of an event prescribed by donor that does not depend on donor's will, or on grounds rendering it voidable under Section 19 ICA — gift validly accepted is otherwise irrevocable), and the family-member concessional stamp-duty discipline applicable in most States. Auto-fires on "draft gift deed", "draft gift", "draft gift instrument", "draft donation deed", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Gift Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: GIFT DEED
instrument_short_code: GIFT_DEED
role_party_1: Donor
role_party_2: Donee
typical_consideration: nil (natural love and affection)
operative_clauses:
  - "Granting clause — *'NOW THIS DEED WITNESSETH THAT in consideration of the natural love and affection that the Donor bears for the Donee, who is the [son / daughter / spouse / parent / sibling / grandchild / other family member or natural object of the Donor's bounty] of the Donor, and without any monetary consideration whatsoever, the Donor hereby GRANTS, CONVEYS, TRANSFERS, ASSIGNS, AND MAKES OVER unto and to the use of the Donee, ABSOLUTELY AND FOREVER, all the right, title, and interest of the Donor in and to the property more particularly described in the Schedule hereto, TO HAVE AND TO HOLD the same as the absolute owner thereof, with all rights, easements, and appurtenances belonging thereto.'*"
  - "Acceptance recital by Donee — *'AND the Donee hereby gratefully accepts the gift made by the Donor of the said property described in the Schedule hereto.'*  (NOTE: Section 122 + Section 129 TPA require ACCEPTANCE during the Donor's lifetime — failing this, the gift is void; acceptance recital + Donee signature on the same instrument satisfies this requirement.)"
  - "Possession clause — *'The Donor has placed the Donee in actual / constructive possession of the said property forthwith from the date of execution hereof, and the Donee has accepted such possession.'*"
  - "Mutation / revenue records — *'The Donor undertakes to facilitate mutation of the property in the revenue records / society records / municipal records in favour of the Donee on registration of this Deed.'*"
  - "Tax compliance — *'The Donor confirms that all property taxes, municipal dues, society dues, electricity and water charges in respect of the said property have been paid up to date.'*"
  - "No future revocation — *'This gift, being validly accepted during the Donor's lifetime, is irrevocable save and except on the grounds specified in Section 126 of the Transfer of Property Act 1882.'*"
stamp_position: "Article 34 of the applicable State Stamp Act Schedule — ad valorem on market value / Ready Reckoner value. Most States offer concessional rates for gifts to blood-relatives (spouse / lineal ascendants / lineal descendants / siblings) — Maharashtra reduces from 5% to ₹200 or 2% per latest notification (verify current rate). Karnataka, Tamil Nadu, Delhi, Gujarat have similar family-member concessions — see State exemplar."
registration_position: "COMPULSORILY REGISTRABLE under Section 17(1)(a) of the Registration Act 1908. Registration before the Sub-Registrar of the area where the property is situated within FOUR MONTHS of execution under Section 23 of the Registration Act."
witness_requirement: "TWO attesting witnesses are MANDATORY under Section 123 TPA 1882 — non-compliance renders the gift VOID (Section 123 is not curable)."
suraj_lamp_check: "GIFT DEED is a valid mode of title transfer to immovable property (along with Sale Deed and registered Will). Suraj Lamp does NOT bar Gift Deeds. The Drafter / Verifier confirms the instrument is a Gift Deed and not a disguised Sale (e.g. Sale dressed as Gift to evade stamp / capital gains)."
```

## Section 122-129 TPA framework summary

- **Section 122** — Definition of "gift". Existing movable / immovable property + voluntary + without consideration + acceptance.
- **Section 123** — Mode of execution. Immovable property: registered instrument + two attesting witnesses. Movable property: registered instrument OR delivery of possession.
- **Section 124** — Gift of future property is VOID.
- **Section 125** — Gift to several persons; one cannot take; that share lapses.
- **Section 126** — Revocation. Gift is revocable only on (a) happening of any specified event not dependent on donor's will, or (b) on grounds rendering the gift voidable under Section 19 ICA (fraud / coercion / undue influence / mistake). Validly accepted gift is otherwise IRREVOCABLE.
- **Section 127** — Onerous gift; donee accepts the whole or rejects the whole.
- **Section 128** — Universal donee — donee personally liable for all donor's debts.
- **Section 129** — Gift mortis causa (gifts in contemplation of death) — special discipline.

## Donor's competence (Section 7 TPA)

The Donor must:

- Be of age of majority (18+, or 21+ in some specific cases under the Indian Majority Act)
- Be of sound mind (Section 12 ICA)
- Not be disqualified by law (e.g. insolvent under IBC Section 3(8) cannot make voluntary transfer)

Where the Donor is elderly or in poor health, the Drafter recommends a medical-fitness certificate at execution + independent-legal-advice recital, to pre-empt opposing heir challenges of mental incapacity / undue influence.

## Hindu coparcener overlay

A Hindu coparcener can make a gift only of his / her undivided share with consent of other coparceners, OR of his / her separate self-acquired property freely. The Drafter checks whether the property is ancestral / coparcenary or self-acquired — for coparcenary property, separate consent recitals are required, OR a Partition Deed should precede the Gift.

## Muslim Hiba overlay

For a Muslim Donor (Hiba):

- Three essentials: declaration (ijab) + acceptance (qubul) + delivery of possession (qabz)
- A Muslim Gift Deed registered under the Registration Act is the recommended form — even though Mussalman Personal Law accepts oral Hiba with three essentials, a registered instrument is evidentiarily sound and required for Section 17 Registration Act compliance for immovable property
- 1/3 rule does NOT apply to inter vivos Hiba (only to wakf-bil-wasiyat / testamentary disposition)

## Common opposing-counsel challenges to a Gift Deed (per Overseer agent)

1. Acceptance during Donor's lifetime not pleaded / not signed
2. Donor's competence challenged (mental incapacity, undue influence)
3. Gift dressed as Sale (or vice versa) for stamp evasion
4. Coparcener property gifted without consent
5. Future property gifted (void under Section 124)
6. Family-member concessional rate claimed without proof of relationship

The Drafter pre-empts these by precise drafting; the Overseer surfaces residual gaps for the advocate's review.
