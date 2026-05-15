---
name: wakf-deed-draft
description: Draft a Wakf Deed (Wakf-bil-Mall during life of Wakif / Wakf-bil-Wasiyat testamentary / Wakf-alal-Aulad family wakf) under the Wakf Act 1995 read with the Mussalman Wakf Validating Act 1913 and Mussalman Personal Law (Shariat) Application Act 1937. Encodes the wakf-essentials (permanent dedication to Almighty Allah; purpose religious / pious / charitable; mutawalli appointment + succession; perpetuity in ultimate purpose — see Mahomed Mohsin v. Sahib Bakar codified in Section 3(r) Wakf Act 1995), the State Wakf Board registration framework (Section 36 Wakf Act 1995), the wakf-bil-wasiyat 1/3 rule (testamentary wakf limited to 1/3 of wakif's property; bequest exceeding 1/3 requires consent of heirs under Mussalman Personal Law), and the Sunni vs Shia sub-school nuances. Auto-fires on "draft wakf deed", "draft wakif declaration", "draft family wakf", "wakf-alal-aulad", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Wakf Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: WAKF DEED
instrument_short_code: WAKF_DEED
role_party_1: Wakif (founder of wakf)
role_party_2: Mutawalli (manager / trustee of wakf)
role_party_3: Beneficiaries (where wakf-alal-aulad — family wakf) / general Muslim public (where wakf-bil-mall / religious wakf)
typical_consideration: none — permanent dedication to Almighty Allah
operative_clauses:
  - "Recital of religious belief — *'WHEREAS the Wakif is a Muslim professing the [Sunni / Shia] sub-school of Mussalman Personal Law, and is desirous of dedicating the property described in Schedule A hereto forever to Almighty Allah for the religious, pious, and charitable purposes hereinafter described, and for the perpetual welfare of the Beneficiaries named in Schedule B hereto.'*"
  - "Declaration of wakf — *'NOW THIS DEED WITNESSETH THAT the Wakif, being of sound mind and acting voluntarily, hereby DEDICATES, RESERVES, AND APPROPRIATES the property described in Schedule A hereto, FOREVER AND IRREVOCABLY, to Almighty Allah, for the religious, pious, and charitable purposes hereinafter set out, the same property hereinafter referred to as the 'Wakf Property'.'*"
  - "Purposes of wakf — *'The Wakf Property shall be administered for the following purposes: (a) [religious purpose — maintenance of masjid / madrasa / mausoleum / Quran recitation / Eid celebrations / Tazia processions]; (b) [pious purpose — Iftar during Ramazan / annual Urs / community Iftar / care of the poor of the community]; (c) [charitable purpose — orphan care / medical aid / education of indigent children / community burial / drinking water provision]; (d) [where wakf-alal-aulad: maintenance and welfare of the Wakif's family — listed Beneficiaries — for so long as they are in need, and on extinction of the family line, the ultimate purpose shall be (a)-(c) above].'*"
  - "Perpetuity in ultimate purpose — *'It is hereby expressly declared that the ultimate purpose of this wakf is religious / pious / charitable, and shall remain so in perpetuity. The Beneficiaries of any wakf-alal-aulad element are entitled to benefit only for so long as the family line subsists; upon extinction of the family line, the entire usufruct shall be applied to the religious / pious / charitable purposes specified above.'*  (NOTE: This perpetuity-in-ultimate-purpose clause is mandatory per Mahomed Mohsin v. Sahib Bakar — codified in Section 3(r) Wakf Act 1995. Family wakf with no ultimate religious / charitable purpose is INVALID.)"
  - "Mutawalli appointment — *'The Wakif appoints [Mutawalli-1] as the first Mutawalli to administer the Wakf Property and to apply the income for the purposes set out herein. The Mutawalli shall hold office during his lifetime / for a fixed term of ___ years / until he resigns or is removed in accordance with this Deed. On the cessation of [Mutawalli-1]'s tenure, the successor Mutawalli shall be: (a) [Successor-Mutawalli-1] / (b) the eldest male / female descendant of [Successor-Mutawalli-1] / (c) such other person as the Wakf Board may, on the application of the Beneficiaries, appoint.'*"
  - "Mutawalli powers and duties — *'The Mutawalli shall: (a) administer the Wakf Property with diligence and good faith; (b) maintain proper accounts and submit annual statements to the State Wakf Board under Section 33 of the Wakf Act 1995; (c) apply the income strictly for the purposes set out herein; (d) make no personal profit from the wakf; (e) refrain from alienating / transferring / mortgaging the Wakf Property save with the prior permission of the State Wakf Board under Section 52 of the Wakf Act 1995.'*"
  - "Wakf Board registration — *'This wakf shall be registered with the State Wakf Board within three months of execution of this Deed under Section 36 of the Wakf Act 1995. The Wakif and the Mutawalli undertake to provide all necessary particulars to the Wakf Board for such registration.'*"
  - "Wakif's separation from Wakf Property — *'The Wakif hereby relinquishes all his / her right, title, and interest in the Wakf Property, save and except such usufruct as may be reserved to the Wakif during his / her lifetime — where reserved, the lifetime usufruct shall not exceed the income / yield of the property and shall not include any right of alienation or revocation.'*"
  - "Indemnity — *'The Wakif and the Mutawalli severally undertake to indemnify the Beneficiaries against any defect in title or any encumbrance on the Wakf Property surfacing post-execution.'*"
stamp_position: "Article 65 / 33 of the applicable State Stamp Act Schedule — concessional rates for religious-charitable wakfs. Most States effectively nominal stamp. Family wakf-alal-aulad attracts higher stamp linked to corpus value (verify State Stamp Act). For testamentary wakf-bil-wasiyat — applicable as a Will (Article on Wills, typically nominal)."
registration_position: "COMPULSORILY REGISTRABLE under Section 17(1)(b) of the Registration Act 1908 (immovable property creating a right or interest of value ₹100 or more). Registration before the Sub-Registrar within FOUR MONTHS of execution under Section 23 Registration Act 1908. ADDITIONALLY, registration with the State Wakf Board under Section 36 of the Wakf Act 1995 within three months of execution."
witness_requirement: "TWO witnesses are routinely taken; ONE is sufficient under Section 59 TPA but TWO are preferred for evidentiary strength."
```

## Wakf Act 1995 + Mussalman Wakf Validating Act 1913 framework

- **Section 3(r) Wakf Act 1995** — definition of "wakf"; permanent dedication of any movable / immovable property by a person professing Islam, for any purpose recognised by Mussalman law as religious, pious, or charitable; includes wakf-alal-aulad to the extent that the ultimate benefit is religious / pious / charitable
- **Section 36** — registration of wakf with the State Wakf Board; failure to register attracts proceedings against the Mutawalli but does not invalidate the wakf
- **Section 51-52** — restrictions on alienation of Wakf Property; alienation without Wakf Board permission is VOID
- **Section 51A** (inserted by the 2013 amendment) — leases of Wakf Property are restricted; long-term leases require Wakf Board approval
- **Section 32-33** — annual statement of accounts to the Wakf Board
- **Section 83** — Wakf Tribunal jurisdiction (the State Wakf Tribunal is the forum for wakf disputes; civil court jurisdiction is barred)
- **Mussalman Wakf Validating Act 1913** — validates wakf-alal-aulad (family wakf) provided the ultimate purpose is religious / pious / charitable

## Three types of wakf

1. **Wakf-bil-Mall (inter vivos religious / public wakf)** — created during the wakif's lifetime, primary purpose religious / pious / charitable
2. **Wakf-bil-Wasiyat (testamentary wakf)** — created by Will; limited to 1/3 of the wakif's property under Mussalman Personal Law; bequest exceeding 1/3 requires consent of heirs
3. **Wakf-alal-Aulad (family wakf)** — created for benefit of wakif's family / descendants, with ultimate purpose religious / pious / charitable; validated by the 1913 Act

## Sunni vs Shia sub-school nuances

- **Sunni** — the wakif may reserve to himself a lifetime usufruct; mutawalli succession typically by male-line; family wakf concept fully recognised
- **Shia** — stricter; wakif cannot reserve usufruct to self; family wakf with delayed religious purpose may be questioned; succession nuances per Ja'fari fiqh

The Drafter loads the wakif's sub-school from `deed-config.md` and applies the appropriate discipline.

## Common challenges to a Wakf Deed (per Overseer agent)

1. **Perpetuity in ultimate purpose not pleaded** — wakf-alal-aulad with NO religious / charitable ultimate purpose is INVALID; counter by mandatory ultimate-purpose clause (as in operative clauses above)
2. **Mutawalli succession ambiguity** — opposing party (or Wakf Board) will challenge; counter by precise mutawalli succession schedule
3. **State Wakf Board registration not effected** — counter by registration-undertaking clause + actual registration within 3 months
4. **1/3 testamentary limit exceeded** (for wakf-bil-wasiyat without heir consent) — heir will challenge; counter by valid heir-consent recital + heir signatures
5. **Wakf used to defeat creditors** — creditor will challenge under fraudulent-transfer principles; counter by solvency declaration + good-faith recital
6. **Section 51 alienation by Mutawalli without Wakf Board permission** — VOID; counter by Mutawalli-duties clause requiring Board permission

## Cross-reference

- For Hindu / Christian / Parsi public charitable trust → out of this plugin's scope (State Public Trusts Act + Charity Commissioner framework)
- For Family Settlement → use `settlement-deed-draft` in this plugin
- For Private Trust under Indian Trusts Act 1882 → use `private-trust-deed-draft` in this plugin
- For testamentary Will (Muslim or otherwise) → use `indian-contracts-drafting/will-draft`
