# Legal Position

`DOCUMENT_ROLE = LEGAL_POLICY_STATE`

This document records the legal posture of the repository. It intentionally does **not** preselect one universal jurisdiction, forum, commercial entity structure, or dispute mechanism for every future situation.

## Current legal posture

`PUBLIC_REPOSITORY = YES`

`SOURCE_AVAILABLE = YES`

`PUBLIC_COMMERCIAL_PERMISSION = NO`

`OPERATIONAL_SKILL_LICENSE = POLYFORM_NONCOMMERCIAL_1_0_0`

`DOCUMENTATION_LICENSE = CC_BY_NC_SA_4_0`

`SEPARATE_COMMERCIAL_LICENSING = ENABLED`

`CONTRIBUTOR_CLA = REQUIRED`

`PR_CLA_ATTESTATION = REQUIRED`

`THIRD_PARTY_PROVENANCE_POLICY = REQUIRED`

`COMMERCIAL_LICENSE_TEMPLATE = AVAILABLE`

## Case-by-case legal choice

The project does not adopt one repository-wide governing law, court, venue, arbitration forum, or commercial structure in advance.

The governing principle is:

~~~text
NO_UNIVERSAL_ADVANCE_JURISDICTION_SELECTION

IF SPECIFIC_SIGNED_AGREEMENT_EXISTS
    -> FOLLOW THAT AGREEMENT TO THE EXTENT LEGALLY EFFECTIVE
ELSE IF DISPUTE_OR_FORMAL_ENFORCEMENT_ARISES
    -> RIGHTS_HOLDER_SELECTS_THE_POSITION_TO_ASSERT
    -> SUBJECT_TO_MANDATORY_APPLICABLE_LAW
    -> SUBJECT_TO_COMPETENT_AUTHORITY
~~~

In practical terms, the rights holder decides how to frame the legal position when a concrete problem exists instead of locking the entire project today to one jurisdiction or forum that may be unsuitable for a future counterparty or dispute.

This is a **reservation of decision**, not a guarantee that a unilateral forum or governing-law preference will always control. Mandatory law, jurisdiction rules, and any binding agreement can limit that choice.

## Commercial agreements

A commercial agreement may define any combination of:

- governing law;
- court or arbitration forum;
- venue;
- controlling language;
- commercial licensor identity;
- payment and invoicing arrangements;
- royalties, revenue share, participation, or fixed fees;
- support and maintenance;
- liability allocation;
- termination and enforcement terms.

Those choices are made for the concrete transaction rather than globally for the repository.

## Contribution-chain requirement

Before accepting third-party contributions:

~~~text
CLA_ACCEPTED?
CONTRIBUTOR_AUTHORITY_CONFIRMED?
THIRD_PARTY_MATERIAL_DISCLOSED?
LICENSE_PROVENANCE_CLEAR?
-> ONLY_THEN MERGE
~~~

This preserves the project's ability to maintain the public licensing model and separately negotiate commercial rights.

## Commercial-deal gate

Before granting commercial rights:

~~~text
LICENSED_MATERIALS IDENTIFIED BY COMMIT/TAG
COMMERCIAL_SCOPE DEFINED
ECONOMIC_TERMS DEFINED
SIGNING_AUTHORITY CONFIRMED
THIRD_PARTY_EXCLUSIONS REVIEWED
CASE_SPECIFIC_LEGAL_TERMS CHOSEN_IF_NEEDED
-> READY_TO_SIGN
~~~

## Review trigger

Revisit this legal posture when a concrete event requires it, such as:

- an external contribution;
- a commercial licensing negotiation;
- a dispute or enforcement question;
- adoption of a trademark or brand asset;
- addition of material third-party content;
- a transaction spanning multiple jurisdictions;
- royalties, equity, revenue share, or material contractual liability.

The repository intentionally keeps case-specific legal choices open until there is an actual case that justifies choosing them.
