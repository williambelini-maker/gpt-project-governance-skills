# Legal Readiness

`DOCUMENT_ROLE = LEGAL_CONFIGURATION_STATE`

This document separates what is already configured from what cannot be safely inferred.

## Configured

`PUBLIC_REPOSITORY = YES`

`PUBLIC_COMMERCIAL_PERMISSION = NO`

`OPERATIONAL_SKILL_LICENSE = POLYFORM_NONCOMMERCIAL_1_0_0`

`DOCUMENTATION_LICENSE = CC_BY_NC_SA_4_0`

`SEPARATE_COMMERCIAL_LICENSING = ENABLED`

`CONTRIBUTOR_CLA = REQUIRED`

`PR_CLA_ATTESTATION = REQUIRED`

`THIRD_PARTY_PROVENANCE_POLICY = REQUIRED`

`COMMERCIAL_LICENSE_TEMPLATE = AVAILABLE`

## Critical unresolved legal variables

These values must not be guessed.

### Rights-holder legal identity

`RIGHTS_HOLDER_LEGAL_NAME = UNSET`

Current public copyright identifier:

`PUBLIC_RIGHTS_HOLDER_IDENTIFIER = williambelini-maker`

For commercial contracts, invoices, enforcement, and formal notices, replace or supplement the public identifier with the actual legal person or legal entity that owns the rights.

### Commercial contact

`PRIVATE_COMMERCIAL_CONTACT = UNSET`

Until configured, `COMMERCIAL_LICENSING.md` directs interested parties to request a private contact channel through GitHub without posting confidential information publicly.

### Governing law

`GOVERNING_LAW = UNSET`

### Exclusive forum / dispute mechanism

`DISPUTE_FORUM = UNSET`

No country, state, court, or arbitration forum should be inferred from repository location, user location, GitHub account location, server location, or language.

### Business/entity structure

`COMMERCIAL_LICENSOR_ENTITY = UNSET`

If commercial licensing becomes material, decide whether contracts are signed by the individual rights holder or by a legal entity that validly owns or licenses the relevant IP.

### Tax and invoicing configuration

`TAX_RESIDENCY_FOR_COMMERCIAL_LICENSING = UNSET`

`INVOICING_ENTITY = UNSET`

These are intentionally not inferred.

## Contribution-chain requirement

Before accepting third-party contributions:

~~~text
CLA_ACCEPTED?
CONTRIBUTOR_AUTHORITY_CONFIRMED?
THIRD_PARTY_MATERIAL_DISCLOSED?
LICENSE_PROVENANCE_CLEAR?
-> ONLY_THEN MERGE
~~~

This matters because the project intends to preserve the ability to offer separate commercial licenses. A contribution that enters without sufficient inbound rights can create a rights gap.

## Commercial-deal gate

Before signing a commercial license:

~~~text
RIGHTS_HOLDER_LEGAL_NAME SET
COMMERCIAL_CONTACT SET
LICENSED_MATERIALS IDENTIFIED BY COMMIT/TAG
COMMERCIAL_SCOPE DEFINED
ECONOMIC_TERMS DEFINED
GOVERNING_LAW SET
DISPUTE_FORUM SET
SIGNING_AUTHORITY CONFIRMED
THIRD_PARTY_EXCLUSIONS REVIEWED
-> READY_TO_SIGN
~~~

## Review trigger

Revisit this file when:

- the first external contributor appears;
- the first commercial licensing inquiry appears;
- a company/entity is formed or becomes the IP holder;
- a trademark or logo is adopted;
- third-party dependencies or substantial external content are added;
- commercial activity crosses jurisdictions;
- revenue, royalties, equity, or material contractual liability becomes significant.
