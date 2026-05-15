---
name: _property_drafting_base
description: Universal Indian property-instrument skeleton. Shared base for all 10 instrument-type drafting skills. Holds the standard structure (Title -> Parties block -> Recitals with title-chain -> Operative Clauses (instrument-type-specific) -> Schedule of Property -> Encumbrance / Title warranties -> Stamping note -> Registration note -> Witnesses -> Signatures). NOT invoked directly — extended by every instrument-type skill in this plugin.
allowed-tools: Read
---

# `_property_drafting_base` — universal Indian property-instrument skeleton

This base skill defines the **structural shape** of any Indian property / conveyancing / inter-vivos transfer / estate instrument drafted by the plugin. Instrument-type skills extend this base with instrument-type-specific operative clauses, witnesses requirements, and stamp / registration framework.

## Universal skeleton

```
1. TITLE
   {{instrument_type.title}} (e.g. "GIFT DEED" / "EXCHANGE DEED" /
   "RELEASE DEED" / "DEED OF DECLARATION OF PRIVATE TRUST" /
   "WAKF DEED" / "DEED OF EASEMENT" / "PARTITION DEED" /
   "FAMILY SETTLEMENT DEED" / "MORTGAGE DEED")

2. PARTIES BLOCK
   THIS DEED is made and executed at {{place_of_execution}} on this
   __ day of {{month}}, {{year}}
   BETWEEN
   [Party-1 full description: full name, age, parentage, religion,
    occupation, full address with PIN, PAN, Aadhaar last 4 digits,
    family particulars relevant to the instrument]
   (hereinafter referred to as the "{{instrument_type.role_party_1}}"
   — Donor / Settlor / Releasor / Wakif / Mortgagor / Transferor /
    Co-owner-1)
   of the FIRST PART
   AND
   [Party-2 full description as above]
   (hereinafter referred to as the "{{instrument_type.role_party_2}}"
   — Donee / Trustee / Beneficiary / Releasee / Mutawalli /
    Mortgagee / Transferee / Co-owner-2)
   of the SECOND PART
   (collectively, the "Parties" and individually, a "Party")

3. RECITALS WITH TITLE-CHAIN NARRATIVE
   WHEREAS [Party-1 acquired the property described in the Schedule
            hereto by way of (purchase from / inheritance from /
            partition with / gift from / will of / settlement from)
            [date / source], duly registered before the Sub-Registrar
            at [SR-Office] vide registration No. ___ dated ____];
   AND WHEREAS [Party-1 has been in continuous, uninterrupted, and
                undisputed possession of the said property since the
                said date of acquisition, has paid all property taxes
                and municipal dues up to date, and has been recognised
                as the absolute owner thereof in the revenue records
                vide Mutation Entry No. ___ dated ____];
   AND WHEREAS [the property is free from all encumbrances, liens,
                mortgages, charges, attachments, lis pendens, and any
                third-party claims, save and except those disclosed
                herein];
   AND WHEREAS [the recitals specific to the instrument type — e.g.
                for Gift: natural love and affection for Donee; for
                Trust: Settlor's intent to create a trust for
                beneficiaries; for Wakf: Wakif's intent to dedicate
                forever to Almighty Allah; for Mortgage: loan / debt
                creating the security need; for Partition: joint
                ownership and intention to divide; for Settlement:
                family arrangement; for Exchange: mutual transfer;
                for Release: relinquishment of rights];
   NOW THIS DEED WITNESSETH AS FOLLOWS:

4. OPERATIVE CLAUSES (instrument-type-specific)
   {{instrument_type.operative_clauses}}

5. SCHEDULE OF PROPERTY HEREIN ABOVE REFERRED TO
   ALL THAT PIECE AND PARCEL of [land / building / flat] admeasuring
   ____ sq. mtrs. / sq. ft., bearing Survey No. ___ / Hissa No. ___ /
   Municipal No. ___ / Plot No. ___, situated at [locality], within
   the registration sub-district of [Sub-Registrar circle], within
   the district of [District], within the State of [State],
   bounded as follows:
       On the North by: [boundary description]
       On the South by: [boundary description]
       On the East by:  [boundary description]
       On the West by:  [boundary description]
   Co-ordinates / Khasra / Khata: [reference where applicable]
   Original registration of title: Sub-Registrar at [SR-Office]
   vide registration No. ___ dated ____.
   Ready Reckoner / Market Value: ₹ ___.

6. ENCUMBRANCE / TITLE WARRANTIES
   The [Transferor / Settlor / Wakif / Mortgagor / Releasor / Co-owners]
   hereby covenant and warrant unto and with the
   [Transferee / Trustee / Mutawalli / Mortgagee / Releasee] that:
   6.1 The Transferor has full power, authority, and title to make
       this transfer / declaration / dedication / settlement.
   6.2 The property described in the Schedule is free from all
       encumbrances, liens, mortgages, charges, attachments, lis
       pendens, claims by any third party, and pending or threatened
       litigation, save and except those disclosed herein.
   6.3 All property taxes, municipal dues, water and electricity
       charges, society / association dues, and other periodic dues
       have been paid up to date.
   6.4 The Transferor undertakes to indemnify and keep indemnified
       the Transferee against any defect in title or any encumbrance
       surfacing post-execution.
   6.5 The Transferor shall do all such acts, deeds, and things as
       may be necessary to perfect title in the Transferee, including
       executing such further documents as may be required by the
       Sub-Registrar / revenue authorities for mutation.

7. STAMPING NOTE
   This instrument is executed on stamp paper of value
   {{stamp_duty}} under Article {{article_no}} of Schedule I of the
   {{applicable_stamp_act}} payable at {{stamp_state}}.

8. REGISTRATION NOTE
   This instrument is compulsorily registrable under Section 17 of
   the Registration Act 1908 [read with Section 17 / 53A of the
   Transfer of Property Act 1882]. Registration to be carried out
   before the Sub-Registrar at {{registration_office}} within four
   months of execution under Section 23 of the Registration Act
   1908.

9. WITNESSES BLOCK
   IN WITNESS WHEREOF the Parties have set their hands to this
   Deed at the place and on the date first above written, in the
   presence of the following Witnesses:

   Witness 1 — [Name / Address / Signature]
   Witness 2 — [Name / Address / Signature]
   (Note: Section 123 TPA requires TWO attesting witnesses for Gift
    Deeds; Section 59 TPA requires TWO attesting witnesses for
    Mortgage Deeds; Section 63 Indian Succession Act 1925 requires
    TWO attesting witnesses for Wills. Other property instruments —
    Release / Partition / Settlement / Trust / Wakf / Easement /
    Exchange — typically require ONE witness but TWO are routinely
    taken for evidentiary safety.)

10. SIGNATURES
    [Party-1 signature with full name and date]
    [Party-2 signature with full name and date]
    [Witness 1 signature]
    [Witness 2 signature]
    [At registration: thumb-impressions, photographs of Parties,
     Sub-Registrar's endorsement, certified copy issued.]
```

## Statute references the plugin handles

- Transfer of Property Act 1882 (Sections 5, 7, 53A, 54, 58-104 [mortgages], 105 [lease], 118-121 [exchange], 122-129 [gift])
- Registration Act 1908 (Sections 17, 17(1A), 23, 49, 32, 32A, 47A)
- Indian Stamp Act 1899 + applicable State Stamp Acts (Schedule I — Articles 5, 6, 23, 24, 32, 34, 40, 55, 58, 61, 65)
- Indian Easements Act 1882 (Sections 4, 13, 15, 25, 35, 52)
- Indian Trusts Act 1882 (Sections 3-30; 14-30 trustee powers and duties)
- Wakf Act 1995 (Sections 3, 36, 51 onwards; Wakf Board framework)
- Mussalman Wakf Validating Act 1913 (validity of family wakf)
- Mussalman Personal Law (Shariat) Application Act 1937
- Hindu Succession Act 1956 (Sections 6, 8; post-2005 amendment daughter-coparcener)
- Indian Succession Act 1925 (Sections 57-191; Chapter III-A Parsi overlay)
- Powers of Attorney Act 1882
- Indian Contract Act 1872 (Sections 7, 14-18 [capacity, consent], 23 [lawful object])
- Specific Relief Act 1963 (Sections 13, 16, 20, 38)
- Bharatiya Sakshya Adhiniyam 2023 (Sections 68 [proof of execution by attesting witness], 130-133)
- Limitation Act 1963 (Articles 58, 59, 62, 63, 64, 65, 110)
- Real Estate (Regulation and Development) Act 2016 (where the property is a RERA-registered project)
- State-specific Apartment Ownership Acts (where the property is a flat)
- State-specific Co-operative Societies Acts (where the transaction involves a CHS)
- State Land Records / Revenue Codes (mutation framework)
