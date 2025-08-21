# Organisations

At a local level social workers will have records of relevant organsiations and safeguarding contacts.

However, there is currently no central register or catalog that meets our needs.

We're exploring approaches to this challenge - essentially a national data infrastructure question.

Our proposal is to compile an initial version of such a registry, drawing on the experise of the network to identify appropriate resources.

## Organsations of interest

Previous work in single view systems has identified the following types of organisations of interest:

|Category|Organisations|
|---|-------|
|Health| GP (Registered surgery)|
||CAMHS / Healthy Young Minds|
||Community Mental Health team|
||Community Nurse / Midwife / Health Visitor|
|Justice|Probation|
||Youth Offending Services|
|Police||
|Tax|Council Tax (Addresses)|
|Education|School|
||School Nurse|
|Housing|Housing associations|
||Temporary housing agencies|

<a href="https://github.com/SocialCareData/taxonomy/issues/new?template=content_issue.yml&title=Organisations%20of%20interest:%20" class="web-button" target="_blank">Raise an issue about organisations of interest</a>

## Defining a register of `Organisations`

FHIR has a resource to describe an [Organisation](https://www.hl7.org/fhir/organization.html), and we can align with this in some areas. However, we propose the following details are required to facilitate more automated data exchange.

|Field name|Cardinality|Data Type & Format|Description & Reasoning|
|-----------------------|-----------|------------------|-----------------------|
|`identifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the organisation.|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the organisation.|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|
|`name`|1 (MUST)|String(UTF-8)|Name of the organisation|
|`type`|1 (SHOULD)|Code: {[WHAT CODES?]}|Type of the organisation e.g. Health, Justice, Education - not strictly necessary for the operation of data exchange but convenient in terms of data collection, stakeholder management and information governance.|
|`status`|0, 1 (MUST)|Code: {[WHAT CODES?]}|The status of the organisation's systems - in terms of ability to make and respond to requests via API.||
|`Verification Status`|1 (MUST)|String(UTF-8)|An indication that the organisation's systems have met the required standards in terms of respsonding to requests.|
|`Verfication Date`|0,1 (MUST)|ISO8601: `YYY-MM-DD`|Date of system verification|
|`Information Governance`|0, 1 (MUST)|Code: {[WHAT CODES?]}|References to the DPAs or legislation governing data sharing for safeguarding purposes|

For operations in data exchange, we anticipate a further set of data requirements (not public facing):

|Field name|Cardinality|Data Type & Format|Description & Reasoning|
|-----------------------|-----------|------------------|-----------------------|
|`identifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the organisation.|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the organisation.|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|
|`System Provider`|1 (MUST)|String(UTF-8)|Name of the system supplier|
|`System Version`|1 (MUST)|String(UTF-8)|Name of product and version of system|
|`Request Test`|1 (MUST)|Code: {[WHAT CODES?]}|Indicator that system passes data request tests satisfactorily|
|`Response Test`|1 (MUST)|Code: {[WHAT CODES?]}|Indicator that the system responds to requests satisfactorily|
|`API endpoints`|1 (MUST)|Code: {[WHAT CODES?]}|Operational endpoints for data exchange|

<a href="https://github.com/SocialCareData/taxonomy/issues/new?template=content_issue.yml&title=Organisations%20Register:%20" class="web-button" target="_blank">Raise an issue about register of organisations</a>