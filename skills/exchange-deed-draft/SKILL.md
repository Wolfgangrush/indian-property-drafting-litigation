---
name: exchange-deed-draft
description: Draft an Exchange Deed under Sections 118-121 of the Transfer of Property Act 1882, compulsorily registrable under Section 17(1)(b) of the Registration Act 1908 (where the value is ₹100 or more). Encodes the Section 118 definition (mutual transfer of ownership in one thing for ownership in another thing), the Section 119 rights and liabilities on exchange (each Party with the rights and liabilities of a Seller as to what he is giving and of a Buyer as to what he is taking), the Section 120 rights of party deprived of thing received, the Section 121 exchange of money discipline, and the dual-stamp discipline (each leg of the exchange separately stamped — both Schedule A and Schedule B properties attract ad valorem stamp under the applicable State Stamp Act). Auto-fires on "draft exchange deed", "draft property exchange", "draft mutual transfer deed", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Exchange Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: EXCHANGE DEED
instrument_short_code: EXCHANGE_DEED
role_party_1: First Exchanger
role_party_2: Second Exchanger
typical_consideration: mutual transfer + cash equalisation (where one property is of higher value)
operative_clauses:
  - "Mutual transfer clause — *'NOW THIS DEED WITNESSETH THAT in pursuance of the mutual covenant and the consideration of the mutual transfer effected hereby, the First Exchanger hereby GRANTS, CONVEYS, TRANSFERS, ASSIGNS, AND MAKES OVER unto and to the use of the Second Exchanger ABSOLUTELY AND FOREVER all the right, title, and interest of the First Exchanger in and to the property more particularly described in Schedule A hereto; AND in consideration thereof, the Second Exchanger hereby GRANTS, CONVEYS, TRANSFERS, ASSIGNS, AND MAKES OVER unto and to the use of the First Exchanger ABSOLUTELY AND FOREVER all the right, title, and interest of the Second Exchanger in and to the property more particularly described in Schedule B hereto.'*"
  - "Equality of value / cash equalisation — *'The Parties confirm that the market value of the property in Schedule A is ₹ ___ and the market value of the property in Schedule B is ₹ ___; the difference of ₹ ___ is paid by [First Exchanger / Second Exchanger] to [other Exchanger] by way of cash equalisation, the receipt of which is hereby acknowledged.'*  (Where there is no cash equalisation: 'The Parties confirm that the values are equal and that no cash equalisation is being effected.')"
  - "Possession exchange — *'The Parties have, on the date of execution hereof, exchanged actual / constructive possession of the said properties as described in Schedules A and B respectively.'*"
  - "Section 119 TPA rights — *'Each Party shall have, in respect of the property received by him, the rights of a Buyer; and in respect of the property given by him, the obligations of a Seller, under the Transfer of Property Act 1882 and any other applicable law.'*"
  - "Section 120 TPA covenant — *'Each Party warrants the marketable title to the property he transfers herein; if a Party is by reason of any defect in the other Party's title deprived of the property received by him, the deprived Party shall be entitled, at his option, to compensation in money or to the return of the property given by him.'*"
  - "Tax compliance — *'Both Parties confirm that all property taxes, municipal dues, society dues, electricity and water charges in respect of the said properties have been paid up to date.'*"
stamp_position: "DUAL STAMP discipline — each leg of the exchange separately stamped under Article 32 (or equivalent) of the applicable State Stamp Act, ad valorem on the respective property's market value / Ready Reckoner value. A single composite stamp on the higher-valued property is NOT sufficient; the Sub-Registrar will refuse registration."
registration_position: "COMPULSORILY REGISTRABLE under Section 17(1)(b) of the Registration Act 1908 where the value of the right transferred is ₹100 or more (which it will be for any meaningful Exchange Deed). Registration before the Sub-Registrar of the area where the property (or properties) are situated within FOUR MONTHS of execution. Where the two properties are in different Sub-Registrar circles, registration may be required at both circles (verify State Registration Manual)."
witness_requirement: "ONE witness is required by Section 59 TPA + practice; TWO witnesses are routinely taken for evidentiary safety. (Note: Section 123 TPA's two-witness mandate is GIFT-specific and does not extend to Exchange.)"
```

## Section 118-121 TPA framework summary

- **Section 118** — Definition of "exchange". Mutual transfer of ownership in one thing for ownership in another thing, neither thing or both being money. (Where one thing is money, the transaction is a Sale of the other thing for that price.)
- **Section 119** — Each Party has, in respect of the thing given, the rights and is subject to the liabilities of a Seller (under the TPA Sale chapter); and in respect of the thing taken, the rights and liabilities of a Buyer.
- **Section 120** — Right of party deprived of thing received in exchange. If the Party is by reason of any defect in the title of the other Party deprived of the thing received in exchange, that Party is, at his option, entitled to either compensation in money OR the return of the thing transferred by him.
- **Section 121** — Exchange of money for money attracts both Sections 118 + 119 to the extent applicable.

## Common challenges to an Exchange Deed (per Overseer agent)

1. **Single stamp instead of dual stamp** — Sub-Registrar will refuse registration; the dual-stamp discipline must be respected
2. **Disguised Sale Deed** — opposing party will allege the transaction is really a Sale (where there is significant value imbalance with cash equalisation); counter by equality-of-value or fair-cash-equalisation recital
3. **Defect in title of one leg** — opposing party will invoke Section 120 TPA to seek return / compensation; counter by clean title-chain on both legs
4. **Possession of one leg not exchanged** — opposing party will allege incomplete transfer; counter by simultaneous-possession-exchange clause
5. **Family-member exchange for stamp evasion** — where one property is of significantly higher value and the cash equalisation is unrealistically low, Sub-Registrar may refer the matter to the Collector under Section 47A Indian Stamp Act 1899 for revenue protection

## Exchange vs Barter — TPA terminology

Section 118 TPA uses "exchange" to mean what general law calls "barter" — neither thing or both being money. Cash equalisation is acceptable so long as the dominant character of the transaction is mutual property transfer, not money-for-property.

## Personal-law overlays

- **Hindu coparcenary property** — both legs need consent of all coparceners, OR a Partition Deed precedes the Exchange
- **Muslim** — Muslim law accepts Exchange (al-Sarf) — apply Section 118 TPA where the underlying property is immovable

## Cross-reference

- For Sale of a property (one thing for money) → use `indian-contracts-drafting/sale-deed-draft`
- For Sale + Repurchase combination → that's two separate Sale Deeds, not an Exchange
- For partition between coparceners → use `partition-deed-draft` in this plugin
- For family settlement with mutual rights adjustment → use `settlement-deed-draft` in this plugin
