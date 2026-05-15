---
name: private-trust-deed-draft
description: Draft a Private Trust Deed under the Indian Trusts Act 1882, declaring a private trust (as distinct from a public charitable trust which is governed by the Charitable and Religious Trusts Act 1920 / applicable State Public Trusts Acts / Charity Commissioner framework). Encodes the three-certainties rule (Section 6 + 9 ITA — certainty of intention, certainty of subject-matter, certainty of beneficiary), the Section 5 ITA registration requirement (immovable property trusts require registered instrument), the Section 10-18 trustee competence and powers, the Section 14-30 trustee duties (act in good faith / careful inspection / accounts / no profit / impartiality between beneficiaries), and the Section 56-65 termination / revocation framework. Auto-fires on "draft trust deed", "draft private trust", "draft family trust", "draft inter vivos trust", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Private Trust Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: DEED OF DECLARATION OF PRIVATE TRUST
instrument_short_code: PRIVATE_TRUST_DEED
role_party_1: Settlor (Author of the Trust)
role_party_2: Trustees (initial trustees named in the deed)
role_party_3: Beneficiaries (named or class-described)
typical_consideration: trust corpus transferred from Settlor to Trustees; no monetary consideration to Settlor
operative_clauses:
  - "Declaration of trust — *'NOW THIS DEED WITNESSETH THAT the Settlor, being desirous of providing for the welfare and benefit of the Beneficiaries hereinafter named, and reposing full confidence in the Trustees, hereby DECLARES, ESTABLISHES, AND SETTLES the trust hereinafter described, and transfers, assigns, and conveys to the Trustees the trust property described in Schedule A hereto, TO HOLD the same UPON TRUST for the Beneficiaries upon the terms and conditions set out herein.'*"
  - "Name of trust — *'This trust shall be known as the [Trust Name] Private Trust.'*"
  - "Trust property (corpus) — *'The trust property consists of (a) the immovable property described in Schedule A hereto, and (b) the movable property / cash deposit of ₹ ___ described in Schedule B hereto, hereinafter collectively the Trust Corpus.'*  (Where the trust is initiated with cash deposit + future additions: 'The Trustees are empowered to accept further additions to the Trust Corpus from the Settlor, from the Beneficiaries, or from any other person, subject to acceptance by the Trustees.')"
  - "Beneficiaries — *'The Beneficiaries of this Trust are: [list of named Beneficiaries with relationship to Settlor + date of birth where Beneficiaries are minors], and the share / interest of each Beneficiary is as set out in Schedule C hereto.'* (Where the trust is for a class — e.g. grandchildren of the Settlor — the class is described with sufficient certainty.)"
  - "Trust purposes — *'The Trustees shall hold the Trust Corpus upon the following trusts: (a) to apply the income for the maintenance, education, medical care, and welfare of the Beneficiaries; (b) to invest the Trust Corpus in such authorised investments as the Trustees may determine; (c) on each Beneficiary attaining the age of ___ years / on such other event as specified herein, to transfer the Beneficiary's share of the Trust Corpus to the Beneficiary absolutely; (d) such other purposes consistent with the welfare of the Beneficiaries as the Trustees may determine in good faith.'*"
  - "Trustees — *'The initial Trustees are [Trustee-1], [Trustee-2], and [Trustee-3], who have accepted the trust and confirmed their willingness to discharge the duties of Trustees by signing this Deed as 'Trustees'. The Trustees shall hold office during their lifetime / for a fixed term of ___ years / until they retire under Clause ___ / until they are removed in accordance with Clause ___. The minimum number of Trustees at any time shall be ___; the maximum number shall be ___.'*"
  - "Trustee powers — *'The Trustees shall have, in addition to the powers conferred by the Indian Trusts Act 1882, all such powers as are necessary or convenient for the proper administration of the trust, including the power to: (a) invest the Trust Corpus in [authorised investments — fixed deposits / government securities / mutual funds / equity per ISA 1875 + applicable State regulations]; (b) collect rents / dividends / interest on Trust Corpus; (c) maintain accounts and engage auditors; (d) defend and prosecute legal proceedings in respect of the Trust; (e) pay taxes, statutory dues, and expenses of administration; (f) delegate ministerial duties to professionals; (g) appoint and remove successor Trustees subject to the Settlor's confirmation during his lifetime.'*"
  - "Trustee duties — *'The Trustees shall: (a) act in good faith and with reasonable diligence (Section 15 ITA); (b) inform Beneficiaries of the state of the trust (Section 18 ITA); (c) keep accurate accounts and submit them annually (Section 20 ITA); (d) not derive any personal profit from the trust (Section 17 ITA); (e) act impartially as between Beneficiaries (Section 19 ITA); (f) protect the Trust Corpus from waste / damage / loss (Section 16 ITA).'*"
  - "Accounts and audit — *'The Trustees shall maintain proper books of account and shall cause the same to be audited annually by a qualified chartered accountant; audited statements shall be made available to all Beneficiaries.'*"
  - "Variation and termination — *'The Settlor reserves the right during his lifetime to vary the terms of this Trust by registered Deed of Variation, subject to the consent of all major Beneficiaries. After the Settlor's lifetime, the Trust shall not be variable except as provided in Section 11 ITA or as otherwise ordered by the competent civil court. The Trust shall stand terminated on the happening of [specified termination event] / on transfer of the entire Trust Corpus to the Beneficiaries.'*"
stamp_position: "Article 64 / 65 of the applicable State Stamp Act Schedule — linked to trust corpus value. Many States offer concessional rates where the trust is for family-Beneficiaries. Maharashtra: ad valorem on corpus (verify current rate)."
registration_position: "COMPULSORILY REGISTRABLE under Section 5 of the Indian Trusts Act 1882 read with Section 17(1)(b) of the Registration Act 1908, where the trust corpus includes immovable property. For movable-only trust corpus, registration is not compulsory but is recommended for evidentiary value. Registration before the Sub-Registrar of the area where the immovable property is situated within FOUR MONTHS of execution under Section 23 Registration Act 1908."
witness_requirement: "TWO witnesses are routinely taken (one is sufficient under Section 59 TPA + practice)."
```

## Section 6 + 9 ITA three certainties

For a valid trust to come into existence:

- **Certainty of intention** — Settlor must clearly intend to create a trust (Section 6); precatory expressions like *"I wish my children to be looked after"* are insufficient
- **Certainty of subject-matter** — the trust property must be identifiable and described with reasonable particularity (Section 7)
- **Certainty of object (beneficiary)** — the beneficiary must be named or be a member of a class describable with reasonable certainty (Section 9); a trust for *"such persons as the Trustees may deem deserving"* is too vague

Failure of any certainty → no trust comes into existence; the property reverts to the Settlor (resulting trust under Section 81-94 ITA).

## Trustee competence — Section 10 ITA

Trustees must be:

- Of sound mind and competent to contract (Section 11 ICA)
- Not subject to legal disability under any law
- Willing to accept the trust (Section 11 ITA — acceptance is essential, can be expressed by signature on the Deed or by acting under the trust)

Where any of the named Trustees is a corporation / institution, the corporation's authorising resolution + power to act as trustee is referenced.

## Section 14-30 ITA trustee duties (codified in operative clauses above)

The Drafter expressly incorporates ITA 1882 trustee-duties framework into the Deed so that any future dispute is resolved by reference to the codified duties + the Deed's specific provisions.

## Tax discipline

A Private Trust is taxed under Sections 161-164 of the Income-tax Act 1961:

- **Determinate beneficiary trust** (Section 161) — beneficiary's individual share taxed at beneficiary's slab rate
- **Indeterminate beneficiary trust** (Section 164) — taxed at maximum marginal rate (MMR)
- **Discretionary trust** — Section 164(1) applies — MMR

The Drafter notes the tax position in the Deed and recommends that the Settlor consult tax counsel for the specific tax profile.

## Common challenges to a Private Trust Deed (per Overseer agent)

1. **Vague Beneficiary description** — opposing party will challenge under Section 9 ITA certainty; counter by precise Beneficiary identification
2. **Trustee acceptance signatures missing** — counter by signature recital + acceptance clause
3. **Indeterminate purpose** — opposing party will challenge under Section 4 ITA / Section 23 ICA; counter by precise purpose enumeration
4. **Disguised Gift** — opposing party will allege the Trust is really a Gift dressed as a Trust; counter by genuine trustee-management structure + ongoing duties + audit
5. **Coparcener property in Trust** — Hindu coparcener cannot settle ancestral property in trust without consent of other coparceners; counter by self-acquired declaration / coparcener-consent

## Cross-reference

- For **Public Charitable Trust** — separate framework under State Public Trusts Act + Charity Commissioner (out of this plugin's scope; can be added in v0.2)
- For **Wakf** — use `wakf-deed-draft` in this plugin
- For **Family Settlement** — use `settlement-deed-draft` in this plugin (different framework, different stamp rate)
- For **inter-vivos Gift without trust structure** — use `gift-deed-draft` in this plugin
