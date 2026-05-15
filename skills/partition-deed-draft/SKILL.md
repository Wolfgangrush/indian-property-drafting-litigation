---
name: partition-deed-draft
description: Draft a Partition Deed for private partition between coparceners / co-owners of joint-family or joint-tenancy property, OUTSIDE the court (distinct from a partition suit under Order 34 CPC). Encodes the Section 7 Indian Stamp Act 1899 partition discipline (stamp on highest-share-aggregate-rate basis), the Hindu Succession Act 1956 framework (Mitakshara vs Dayabhaga schools; post-2005-amendment daughter-as-coparcener), the Mussalman Personal Law (Shariat) Application Act 1937 inheritance framework for Muslim co-heirs, and the conveyancing register for declarative partition (the Deed RECITES the existing rights and DECLARES the partition — it does not CONVEY title; partition is a metes-and-bounds division of pre-existing co-ownership). Auto-fires on "draft partition deed", "draft family partition", "draft coparcener partition", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Partition Deed Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_property_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Instrument metadata

```yaml
instrument_type_line: PARTITION DEED
instrument_short_code: PARTITION_DEED
role_party_1: Co-owner-1 (or First Coparcener / First Co-sharer)
role_party_2: Co-owner-2 (or Second Coparcener / Second Co-sharer)
role_party_N: Additional Co-owners as required
typical_consideration: nil (declarative partition — no consideration; mutual recognition of existing shares)
operative_clauses:
  - "Recital of joint ownership / coparcenership — *'WHEREAS the Parties are members of [the joint Hindu family / the Muslim co-heirs / a joint-tenancy / a tenancy-in-common] and have been jointly entitled to the property described in the Schedule hereto by virtue of [origin of joint right — partition / inheritance / joint purchase / family settlement] dated ____, as more particularly described in the Recitals hereto.'*"
  - "Pre-partition share recital — *'AND WHEREAS the shares of the Parties in the said joint property are as follows: [Co-owner-1] — [share-fraction]; [Co-owner-2] — [share-fraction]; [Co-owner-N] — [share-fraction]; aggregating to the whole.'*  (For Hindu coparceners post-2005: include daughters / sons as coparceners with equal shares. For Muslim heirs: apply applicable Sunni / Shia inheritance schedule.)"
  - "Intent to partition — *'AND WHEREAS the Parties have decided to partition the said property by metes and bounds, so that each Party shall hold and enjoy his / her allotted share absolutely and exclusively henceforth, and the joint character of the property shall stand extinguished.'*"
  - "Declaration of partition — *'NOW THIS DEED WITNESSETH THAT the Parties have, by mutual agreement and consent and in pursuance of the said intent to partition, partitioned the said joint property as follows: (a) the portion described in Schedule-A1 hereto, admeasuring ___, is allotted to [Co-owner-1] absolutely and exclusively; (b) the portion described in Schedule-A2 hereto, admeasuring ___, is allotted to [Co-owner-2] absolutely and exclusively; (c) [further allotments for each Co-owner].'*"
  - "Confirmation of possession — *'Each Party has, on the date of execution hereof, taken actual / constructive possession of the portion allotted to him / her, and is henceforth the absolute and exclusive owner of the said portion, with full power of alienation, disposal, and bequest.'*"
  - "Extinguishment of joint rights — *'The joint character of the said property is hereby extinguished. Each Party releases, relinquishes, and forever quitclaims all right, title, share, and interest in the portions allotted to the other Parties. No Party shall hereafter claim any joint right or share in any portion not allotted to him / her under this Deed.'*"
  - "Equality adjustment (where applicable) — *'Where the partition is not in strict mathematical proportion to the shares, the Parties have agreed to the following adjustment: [Co-owner with shortfall] receives an additional [cash payment / movable property / different immovable portion] of value ₹ ___ from [Co-owner with surplus], to equalise the shares; the receipt of which is hereby acknowledged.'*"
  - "Mutation — *'The Parties undertake to apply for mutation in the revenue records / society records / municipal records to reflect the partition as effected herein, and to provide all necessary documents to the concerned authorities.'*"
  - "Indemnity — *'Each Party undertakes to indemnify the other Parties against any claim, demand, action, or proceeding in respect of the portion allotted to him / her, from any third party claiming through or under that Party.'*"
stamp_position: "SECTION 7 INDIAN STAMP ACT 1899 — Partition Deed stamp duty is computed on the highest-share-aggregate-rate basis. That is: stamp duty is calculated on the aggregate value of the share with the highest value (treating that share as if it were a separately conveyed property at ad valorem rate), with the State Stamp Act overrides for concessional rates among coparceners. Most States offer significant concessions for Hindu coparcener partitions and for Muslim heir partitions. Verify current notification under State exemplar."
registration_position: "COMPULSORILY REGISTRABLE under Section 17(1)(b) Registration Act 1908 (a partition affects rights and title of value ₹100 or more in the joint property). Registration before the Sub-Registrar of the area where the property is situated within FOUR MONTHS of execution under Section 23 Registration Act 1908. UN-REGISTERED Partition Deeds are receivable only as COLLATERAL EVIDENCE of severance of joint status, not for title to specific portions — Section 49 Registration Act."
witness_requirement: "ONE witness is sufficient (Section 59 TPA + practice); TWO witnesses are routinely taken."
```

## Section 7 Indian Stamp Act 1899 partition discipline (mandatory)

**Section 7** prescribes that stamp duty on a partition is on the BASIS OF THE HIGHEST-SHARE-AGGREGATE. That is: identify the share allotted to the largest-share recipient; compute the ad-valorem stamp on the aggregate value of that share; the entire partition is stamped on that single highest-share basis.

This is significantly less than the cumulative stamp that would be payable if each share were separately conveyed.

State Stamp Acts further reduce this — Maharashtra, for instance, offers concessional rates among coparceners (verify current notification). Sub-Registrar / Stamp Authority will scrutinise; under-foot may attract Section 47A reference to the Collector.

## Hindu Succession Act 1956 framework

- **Mitakshara school** (most of India) — coparcenership by birth; the joint family property is co-owned by all coparceners by birth; partition is by metes and bounds
- **Dayabhaga school** (Bengal, parts of Assam) — coparcenership only on father's death; the father is the absolute owner during his lifetime
- **Post-2005 amendment** (Hindu Succession (Amendment) Act 2005) — daughters of coparceners are coparceners BY BIRTH on equal terms with sons; *Vineeta Sharma v. Rakesh Sharma* (2020) 9 SCC 1 confirms retrospective applicability
- For Hindu coparcener partition: confirm all coparceners (including daughters post-2005) are Parties to the Deed; absence of any coparcener renders the partition incomplete

## Mussalman Personal Law (Shariat) inheritance framework

- Muslim co-heirs hold property as tenants-in-common from the moment of the ancestor's death (no joint-family / no coparcener concept like Hindu)
- Sunni vs Shia sub-schools — different inheritance schedules
- The partition of Muslim co-heirs' property is a normal Section 7 Indian Stamp Act partition; concessional rates apply in most States

## Christian / Parsi co-heir framework

- Indian Succession Act 1925 framework — tenants-in-common by inheritance; partition follows normal Section 7 Indian Stamp Act regime

## Common challenges to a Partition Deed (per Overseer agent)

1. **Section 7 highest-share-aggregate mis-computation** — Sub-Registrar / Stamp Authority will refer to Collector under Section 47A; counter by precise computation worksheet
2. **Missing coparcener (especially post-2005 daughter)** — opposing daughter / sister will challenge the partition as void; counter by full coparcener list + signature
3. **Disguised Gift / Sale** — Sub-Registrar may allege the partition is really a Gift or Sale (where shares are wildly disproportionate to legal shares); counter by legal-share-aggregate recital + equalisation-payment recital
4. **Self-acquired vs ancestral property** — opposing party will challenge whether the property is joint-family / ancestral or self-acquired (only joint-family / ancestral property is subject to partition); counter by origin-of-title recital
5. **Mutation not effected** — opposing party will allege partition is paper-only; counter by mutation-undertaking clause + actual mutation application

## Cross-reference

- For partition by court decree → out of this plugin's scope (file under Order 34 CPC; use `district-court-drafting`)
- For Family Settlement (vs full partition) — use `settlement-deed-draft` in this plugin
- For Release of share post-partition — use `release-deed-draft` in this plugin
- For Will distributing post-partition self-acquired property → use `indian-contracts-drafting/will-draft`
