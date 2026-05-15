---
name: easement-deed-draft
description: Draft an Easement Deed under the Indian Easements Act 1882 — granting an easement of right of way, right to light and air, right to water, right of support, or any other easement of one tenement over another. Encodes the Section 4 IEA definition (right of dominant tenement owner over servient tenement), the Section 7 IEA exclusion of natural rights, the Section 8-12 IEA acquisition framework (express grant / implied grant on severance / prescription / customary), the Section 13 IEA quasi-easement upon severance of unity of ownership, the Section 15 IEA prescription requirement of 20 years' open / peaceful / uninterrupted / continuous enjoyment, the Section 35 IEA easement extinguishment framework, and the Section 52 IEA distinction between easement (interest in land) and licence (personal permission). Auto-fires on "draft easement deed", "draft right of way", "draft easement grant", "grant of easement", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Easement Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: DEED OF EASEMENT
instrument_short_code: EASEMENT_DEED
role_party_1: Servient Owner (owner of the property over which the easement is granted)
role_party_2: Dominant Owner (owner of the property in whose favour the easement is granted)
typical_consideration: nominal (for natural love and affection / for separate consideration in arm's length grants)
operative_clauses:
  - "Identification of dominant + servient tenements — *'WHEREAS the Dominant Owner is the absolute owner of the immovable property described in Schedule A hereto (hereinafter the 'Dominant Tenement'), AND WHEREAS the Servient Owner is the absolute owner of the immovable property described in Schedule B hereto (hereinafter the 'Servient Tenement'), and the Dominant Tenement is contiguous to / adjoining / abutting the Servient Tenement.'*"
  - "Nature of easement — *'NOW THIS DEED WITNESSETH THAT in consideration of [natural love and affection / a sum of ₹ ___ paid by the Dominant Owner to the Servient Owner], the Servient Owner hereby GRANTS unto the Dominant Owner, his / her heirs, legal representatives, successors, and assigns, FOREVER, the following easement over the Servient Tenement: [precise description of easement — e.g. *right of way of width ___ feet from point A to point B as shown in the plan annexed as Schedule C / right of light and air through specified apertures / right to draw water from the well situated at point X / right of support to the building situated on the Dominant Tenement from the adjoining wall on the Servient Tenement / right to discharge water through the drain at point Y*].'*"
  - "Classification of easement — *'The easement hereby granted is: (a) a [continuous / discontinuous] easement under Section 5 IEA 1882; (b) an [apparent / non-apparent] easement under Section 5 IEA 1882; (c) a [positive / negative] easement under Section 5 IEA 1882; (d) [in perpetuity / for the lifetime of the Dominant Owner / for a fixed term of ___ years from the date hereof].'*"
  - "Manner of enjoyment — *'The Dominant Owner shall be entitled to enjoy the easement in the manner reasonably necessary for the use of the Dominant Tenement, and the Servient Owner shall not do, or permit to be done, anything that would obstruct or interfere with the easement. The Dominant Owner shall: (a) not enlarge or alter the easement to the prejudice of the Servient Owner; (b) maintain the easement in a state of reasonable repair at the Dominant Owner's expense; (c) cause no unnecessary inconvenience to the Servient Owner in exercising the easement.'*"
  - "Servient Owner's obligations — *'The Servient Owner shall: (a) permit peaceful enjoyment of the easement by the Dominant Owner; (b) not obstruct, narrow, or otherwise interfere with the easement; (c) not erect any construction over the easement that would diminish its utility; (d) keep the Servient Tenement in such state as is reasonably necessary to support the easement.'*"
  - "Disturbance and remedy — *'In the event of any disturbance to the easement, the Dominant Owner shall be entitled to (a) seek mandatory injunction under Order 39 Rules 1 + 2 CPC 1908 read with the Specific Relief Act 1963; (b) recover damages under Section 35 IEA 1882 read with the Specific Relief Act 1963.'*"
  - "Extinguishment recital — *'The easement shall be extinguished only on the grounds specified in Sections 37 to 47 of the Indian Easements Act 1882 — release, unity of ownership of both tenements, abandonment for 20 years, expiry of fixed term, destruction of dominant or servient tenement, and similar statutory grounds.'*"
stamp_position: "Article 5(a) of the applicable State Stamp Act Schedule (treating Easement Deed as an Agreement) — nominal stamp; or specific Article for Easement where the State Stamp Act prescribes (verify State exemplar). Most States treat Easement Deed at nominal stamp where there is no significant consideration."
registration_position: "COMPULSORILY REGISTRABLE under Section 17(1)(b) Registration Act 1908 where the easement creates an enduring right of value ₹100 or more (which it will be for any meaningful easement). Registration before the Sub-Registrar of the area where the servient tenement is situated within FOUR MONTHS of execution under Section 23 Registration Act 1908. Easements of short duration / limited value may not require registration but registered easements have stronger evidentiary value."
witness_requirement: "ONE witness is sufficient (Section 59 TPA + practice); TWO witnesses are routinely taken for evidentiary safety."
```

## Indian Easements Act 1882 framework

- **Section 4** — definition of "easement"; right of dominant tenement owner over servient tenement to do or continue to do / prevent or continue to prevent something
- **Section 5** — classifications: continuous / discontinuous; apparent / non-apparent; positive / negative; in perpetuity / for limited term
- **Section 7** — natural rights are excluded (e.g. right of natural support to immovable property is a natural right, NOT an easement)
- **Section 8-12** — acquisition: express grant (registered Deed) / implied grant on severance of unity of ownership / prescription (Section 15) / customary
- **Section 13** — quasi-easements upon severance — where a single owner severs a tenement, easements that were apparent and continuous and necessary for enjoyment of the dominant part PASS by implication to the dominant transferee
- **Section 15** — prescription requires open / peaceful / uninterrupted / continuous enjoyment of the easement for 20 years (30 years against the Government)
- **Section 35** — easement extinguished by destruction / unity of ownership / permanent change in dominant tenement / abandonment / etc.
- **Section 52** — easement vs licence: easement creates an interest in land that runs with the dominant tenement; licence is personal permission revocable at will

## Common easements

1. **Right of way** — most common; precisely described path / width / mode of use (pedestrian / vehicular)
2. **Right to light and air** — through specified windows / apertures of dominant building
3. **Right to water** — to draw from servient tenement's well / tank / stream
4. **Right of support** — to keep dominant building supported by adjoining servient wall / earth
5. **Right to discharge water** — drainage from dominant to servient tenement

## Common challenges to an Easement Deed (per Overseer agent)

1. **Dominant tenement not identified** — Sub-Registrar will refuse registration; counter by precise Schedule A description
2. **Unity of ownership** — if both tenements are owned by the same person, no easement can subsist; counter by separate-ownership recital
3. **Confusion of easement with licence** — opposing party may allege the right granted is a licence (revocable) not an easement (irrevocable interest); counter by enduring-right + heirs-and-assigns recital
4. **Quasi-easement vs full easement** — where the easement arose on severance of unity, opposing party may allege only quasi-easement; counter by Section 13 IEA framework + express-grant recital
5. **20-year prescription challenge** — where the easement is by prescription rather than express grant, opposing party will challenge continuity; counter by witness evidence of uninterrupted use

## Cross-reference

- For Licence (revocable personal permission, not an easement) → typically not a registered instrument; can be drafted as a simple Agreement under `indian-contracts-drafting/_contract_drafting_base`
- For Lease (transfer of right of enjoyment for rent and term) → use `indian-contracts-drafting/lease-deed-draft`
- For Sale of property → use `indian-contracts-drafting/sale-deed-draft`
