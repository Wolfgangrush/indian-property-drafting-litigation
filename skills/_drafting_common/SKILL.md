---
name: _drafting_common
description: Shared reference for all 10 property / conveyancing / estate drafting skills. Holds the anti-pollution rules, the property privacy firewall protocol (party names + property descriptions + Survey/Municipal numbers + consideration figures + Ready Reckoner values + mutation entries substituted with placeholders before downstream AI processing; real-value re-substitution local-only in the Refiner step), the AI-style-marker blacklist, citation discipline, Indian Stamp Act 1899 + State Stamp Act schedule discipline, Registration Act 1908 + Section 17 / 17(1A) + Section 49 / Section 53A TPA discipline, the Suraj Lamp & Industries v. State of Haryana (2012) 1 SCC 656 discipline, the Kale v. Deputy Director (1976) 3 SCC 119 family-settlement framework, Section 7 Indian Stamp Act partition discipline, Indian Trusts Act 1882 three-certainties rule, Wakf Act 1995 + Mussalman Wakf Validating Act 1913 wakf-essentials, Indian Easements Act 1882 dominant-servient-tenement rule, personal-law overlays (Hindu Succession Act 1956 with post-2005 daughter-coparcener amendment / Mussalman Personal Law (Shariat) Application Act 1937 / Indian Succession Act 1925 Christian-Parsi overlay), and the Limitation Act 1963 framework for property suits. NOT invoked directly — referenced from every instrument-type skill in this plugin.
allowed-tools: Read
---

# `_drafting_common` — shared property drafting infrastructure

## Privacy firewall

Property instruments routinely contain highly sensitive material — full names of family members, PAN / Aadhaar identifiers, addresses, family-tree relationships, Survey / Municipal numbers, consideration figures, Ready Reckoner values, mutation entries, encumbrance details, Sub-Registrar registration references. The plugin's privacy discipline:

1. **Reader** substitutes every party name, every PAN / Aadhaar, every Survey / Municipal number, every Sub-Registrar registration reference, every consideration figure, every Ready Reckoner / Market Value, every mutation entry, and every family-tree name with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `deed-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw property descriptions or raw consideration figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `deed-facts.md` and `deed-config.md` so they cannot be committed accidentally.

## AI-style-marker blacklist

Stripped by the Refiner before output:

- Em-dash (`—`) used as sentence-internal pause (replaced with semicolon or comma-bounded clause); however, em-dashes for genuine appositive structures in property recitals are preserved
- Sentence-final *thereby* / *hereby* / *whereby* without an attached verb (note: *"hereby"* and *"thereby"* are STANDARD in conveyancing-register and are preserved; this rule applies only to incorrect uses)
- *Moreover*, *furthermore*, *additionally*, *in addition* as sentence-openers — incompatible with conveyancing register; replaced by *"AND"* / *"AND WHEREAS"*
- *Navigate*, *delve*, *foster*, *robust*, *seamless* (metaphorical uses) — never appear in conveyancing register
- *It is important to note that*, *it should be noted that*, *worthy of note* — replaced with direct recital
- Bullet-list-style structure in operative clauses (operative clauses are numbered paragraphs / firstly-secondly-thirdly enumeration, not bullet lists)

## Citation discipline

The Drafter does **not** generate case names + citations from training memory. Every case citation in any explanatory note or recital must trace to a user-supplied source. Untraceable citations become `[CITATION NEEDED]` placeholders.

Headline cases the Verifier scans for fabrication:

- *Suraj Lamp & Industries (P) Ltd. v. State of Haryana* (2012) 1 SCC 656 — GPA-Sale / Agreement-to-Sell-with-Possession-and-GPA does NOT convey title; the only mode of title transfer of immovable property is a registered Sale Deed
- *Kale v. Deputy Director of Consolidation* (1976) 3 SCC 119 — Family Settlement Deeds — antecedent title not required to be proved; bona fide arrangement; mutual relinquishment
- *Mahomed Mohsin v. Sahib Bakar* — Wakf perpetuity in purpose; codified in Section 3(r) Wakf Act 1995
- *Murarilal v. Devkaran* — Clog on redemption (Section 60 TPA) — void as opposed to public policy
- *Vidhyadhar v. Manikrao* (1999) 3 SCC 573 — Section 53A TPA part-performance
- *State of Karnataka v. Krishna Reddy* — Registration Act under-valuation challenge by Sub-Registrar (Section 47A reference)
- *Naginbhai v. State of Gujarat* — Family settlement vs Partition — Stamp Act demarcation
- *Vasanthi v. Venugopal* — Hindu Coparcener daughter rights post the 2005 amendment

## Indian Stamp Act 1899 + State Stamp Act discipline

Every property instrument under this plugin must be executed on stamp paper of the value prescribed under the applicable State Stamp Act schedule. The Verifier independently computes the stamp duty from:

- `deed_config.stamp_state` (Maharashtra Stamp Act 1958 / Karnataka Stamp Act 1957 / Tamil Nadu Stamp Act / Indian Stamp Act 1899 Delhi-amended / etc.)
- The instrument type (Article in Schedule I)
- The consideration / Ready Reckoner / Market Value
- Family-member concessional rate (where applicable)

Common stamp-duty rules to encode (Maharashtra reference; State-config has the local rates):

- **Gift Deed (Article 34 Maharashtra Stamp Act 1958):** ad valorem on market value; concessional rate (5% reduced to ₹200 or 2% per latest notification) for blood-relative donees (verify current notification)
- **Exchange Deed (Article 32):** ad valorem on the higher-valued property + duplicate stamp for each leg
- **Release Deed (Article 55):** concessional for blood-relative releasor + releasee; ad valorem otherwise
- **Trust Deed (Article 61):** linked to trust corpus value
- **Wakf Deed (Article 65):** religious-charitable concessions in many States
- **Partition Deed (Section 7 Indian Stamp Act 1899):** on highest-share-aggregate-rate basis
- **Settlement Deed (Article 58):** family-settlement concessions in many States
- **Mortgage Deed (Article 40):** ad valorem on secured amount for registered mortgage; nominal for equitable mortgage memorandum (Article 6)
- **Easement Deed (Article 5):** Agreement rate; nominal

## Registration Act 1908 + Section 17 / 17(1A) + Section 49 discipline

Compulsory registration under Section 17 Registration Act 1908:

- Section 17(1)(a) — instruments of gift of immovable property
- Section 17(1)(b) — non-testamentary instruments creating, declaring, assigning, limiting, or extinguishing any right, title or interest in immovable property of value ₹100 or more
- Section 17(1)(c) — non-testamentary instruments acknowledging receipt or payment of consideration for the creation / extinction of such right
- Section 17(1)(d) — leases of immovable property from year-to-year, or for any term exceeding one year, or reserving yearly rent
- Section 17(1A) — agreements-to-sell under Section 53A TPA post-2001 amendment

Consequences of non-registration: Section 49 — the instrument cannot be received as evidence of any transaction affecting such property; collateral-purpose-evidence exception applies (e.g. partition deed receivable as collateral evidence of severance of joint status, but not for title to specific property).

## Suraj Lamp discipline (mandatory)

Per *Suraj Lamp & Industries (P) Ltd. v. State of Haryana* (2012) 1 SCC 656 — a Sale Deed alone, registered under the Registration Act, conveys title to immovable property. The following combinations **do not** convey title:

- GPA-Sale (Power of Attorney coupled with Sale)
- Agreement-to-Sell-with-Possession-and-GPA
- Will-with-GPA
- *"Sale Agreement"* purporting to operate as final conveyance

The Drafter / Verifier independently scan for any such combination in the user's draft request. Where the user wants a GPA, the GPA is restricted to authorisation acts (act on behalf of the principal in court / before authorities / in correspondence) — NOT title transfer.

## Section 53A TPA discipline (agreements to sell)

Post the 2001 amendment, agreements to sell are registrable under Section 17(1A) Registration Act. Section 53A protection requires:

- (a) written and signed contract
- (b) reasonable certainty of terms
- (c) part-performance — possession + (some) payment + readiness to perform on the part of the transferee

Where these are present, the transferor / successor cannot enforce against the transferee any right in respect of the property other than a right expressly provided by the terms of the contract — *Vidhyadhar v. Manikrao* (1999) 3 SCC 573.

## Kale v. Deputy Director Family-Settlement framework

*Kale v. Deputy Director of Consolidation* (1976) 3 SCC 119 — landmark on Family Settlement Deeds:

- Antecedent title is NOT required to be proved
- Bona-fide family arrangement reached by family members to settle existing or future disputes
- Mutual relinquishment of contesting claims
- The settlement creates rights through the recognition of existing rights, not by conveyance
- Public-document recognition is available where the settlement is registered (under Section 17(1)(b) Registration Act 1908)
- Stamp duty under Article 58 (Family Settlement) is typically concessional vs Gift / Sale rates

## Section 7 Indian Stamp Act 1899 partition discipline

Partition Deed stamp duty is computed on the highest of the shares partitioned (with State Stamp Act overrides for concessional rates among coparceners). The "highest share" is the aggregate value of the share allotted to the largest-share recipient.

## Indian Trusts Act 1882 — three certainties

Section 6 ITA: a trust is created when the author:

- Indicates with reasonable certainty the intention to create a trust (certainty of intention)
- The purpose of the trust (certainty of purpose / object)
- The beneficiary (certainty of beneficiary)
- The trust property (certainty of property)
- Transfers the trust property to the trustee

Without all three (intention + property + purpose + beneficiary), no valid trust comes into existence.

## Wakf Act 1995 — wakf-essentials

- Permanent dedication by a person professing Islam, of any movable or immovable property, for any purpose recognised by Mussalman law as religious / pious / charitable
- Dedication is forever (perpetuity in purpose)
- Mutawalli appointment and succession
- Wakf Board registration under Section 36 (failure to register is a ground for proceedings against the wakif / mutawalli but does not invalidate the wakf itself)
- Wakf-bil-wasiyat (testamentary wakf) is limited to 1/3 of the wakif's property under Mussalman Personal Law; bequest exceeding 1/3 requires consent of heirs
- Wakf-alal-aulad (family wakf) is valid only if the ultimate purpose is religious / charitable — see *Mahomed Mohsin v. Sahib Bakar*

## Indian Easements Act 1882 — easement essentials

An easement is the right of the owner of one tenement (the dominant tenement) over the tenement of another (the servient tenement) — to do or continue to do something, or to prevent or continue to prevent something being done, in or upon the servient tenement.

Common easements: right of way, right to light and air, right to water, right of support, right to discharge water. An easement requires:

- Dominant + servient tenement identified
- Two tenements with different ownership (except quasi-easement upon severance of unity of ownership — Section 13)
- Easement creates a right enduring with the dominant tenement

## Personal-law overlays

### Hindu — Hindu Succession Act 1956

- Sections 6 + 8: coparcener rights, intestate succession
- Post-2005 amendment: daughters are coparceners by birth with equal rights as sons (Section 6 as amended)
- *Prakash v. Phulavati* (2016) 2 SCC 36 / *Danamma v. Amar* (2018) 3 SCC 343 / *Vineeta Sharma v. Rakesh Sharma* (2020) 9 SCC 1 — daughter coparcener applies retrospectively
- Mitakshara vs Dayabhaga school — Mitakshara: coparcener right by birth; Dayabhaga: only on father's death
- For Partition / Settlement / Will involving ancestral / coparcenary property: confirm coparcener-share computation under the applicable school + post-2005 daughter inclusion

### Muslim — Mussalman Personal Law (Shariat) Application Act 1937

- For Hiba (Gift): three essentials — declaration (ijab), acceptance (qubul), delivery of possession (qabz)
- 1/3 bequest limit on wakf-bil-wasiyat (testamentary wakf)
- Sunni vs Shia sub-school differences in inheritance and wakf

### Christian / Parsi — Indian Succession Act 1925

- Sections 57-191 framework for Wills
- For Parsi, Chapter III-A overlay (special provisions)

### Sikh / Buddhist / Jain — by default Hindu personal law applies (Section 2 Hindu Succession Act 1956)

## Limitation Act 1963 — property suits framework

| Matter | Article | Period |
|---|---|---|
| Suit for possession of immovable property based on title | Article 65 | 12 years from when possession of defendant becomes adverse |
| Suit for possession on dispossession | Article 64 | 12 years from dispossession |
| Suit for declaration of title | Article 58 | 3 years from when right to sue first accrues |
| Suit to set aside a Gift / Settlement / Mortgage | Article 59 | 3 years from when grounds first known |
| Suit on a mortgage — foreclosure | Article 63 | 12 years from when money becomes due |
| Suit on a mortgage — sale | Article 62 | 12 years from when money becomes due |
| Suit for specific performance of contract | Article 54 | 3 years from date fixed for performance or from when performance refused |
| Suit for partition by a co-owner | Article 110 | 12 years from date of exclusion |
| Suit to set aside a Sale Deed obtained by fraud / undue influence | Article 59 | 3 years from when fraud / undue influence first known |
