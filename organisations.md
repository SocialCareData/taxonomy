# Organisations
Our data exchange infrastructure, at a bare minimum level, involves a social worker sending a query about a person-in-care, the data exchange mechanism directing that query to local and national organisations, and the response being a list of organisations that hold data about that person. This requires a register or catalogue of all organisations that would be data-sharers in the UK, both in the context of social care and in broader person-centric contexts (like policing, education, and more). Such a register/catalogue would have to be centralised, well-maintained, and strongly machine-accessible.

---

#### Organisations of interest

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
|Government|Local Government|
||Central Government|

<a href="https://github.com/SocialCareData/taxonomy/issues/new?template=content_issue.yml&title=Organisations%20of%20interest:%20" class="web-button" target="_blank">Raise an issue about organisations of interest</a>

---

## Aligning with the Organisation Data Service (ODS)

While we could make our own register/catalogue, an ongoing design principle of our work is to re-use existing data standards where possible. Here, we identified the [NHS England Organisation Data Service (ODS)](https://www.odsdatasearchandexport.nhs.uk/) as a potential standard for re-use.

The ODS serves as an API to search for organisations and practitioners in the UK Health and Social Care system. It is built on top of FHIR, with a comprehensive [data model](https://www.odsdatasearchandexport.nhs.uk/referenceDataCatalogue/index.html) that enables organisations to be clearly described and categorised. The underlying register of organisations is regularly maintained, refreshed at 2am every night.

Our requirements for a register/catalogue, at a technical level, may extend beyond what is served by the ODS, but that is not to say that we cannot use ODS as a starting point, a foundation for our own standard. To examine this further, we designed the required fields we had for organisations below, and then compared where there was alignment with ODS and where there was misalignment. Findings will be discussed in the following sections.

Beyond technical information, though, we must ascertain whether ODS is perfectly suitable for our use case. Does it contain all organisations/types of organisations in the social care ecosystem? Does it contain adequate information about the roles these organisations carry out? Is the register complete, accurate, and disambiguated? This is an area of ongoing exploration.


## Defining a register of `Organisations`

FHIR has a resource to describe an [Organisation](https://www.hl7.org/fhir/organization.html), and we can align with this in some areas. However, we propose the following details are required to facilitate more automated data exchange.

|Field name|Cardinality|Data Type & Format|Description & Reasoning|
|-----------------------|-----------|------------------|-----------------------|
|`organisationIdentifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the organisation.|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the organisation.|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|
|`organisationName`|1 (MUST)|String(UTF-8)|Name of the organisation|
|`organisationType`|1 (SHOULD)|Code: {[WHAT CODES?]}|Type of the organisation e.g. Health, Justice, Education - not strictly necessary for the operation of data exchange but convenient in terms of data collection, stakeholder management and information governance.|
|`Status`|0, 1 (MUST)|Code: {[WHAT CODES?]}|The status of the organisation's systems - in terms of ability to make and respond to requests via API.|
|`Verification Status`|1 (MUST)|String(UTF-8)|An indication that the organisation's systems have met the required standards in terms of respsonding to requests.|
|`Verfication Date`|0,1 (MUST)|ISO8601: `YYY-MM-DD`|Date of system verification|
|`Information Governance`|0, 1 (MUST)|Code: {[WHAT CODES?]}|References to the DPAs or legislation governing data sharing for safeguarding purposes|

For operations in data exchange, we anticipate a further set of data requirements (not public facing):

|Field name|Cardinality|Data Type & Format|Description & Reasoning|
|-----------------------|-----------|------------------|-----------------------|
|`System Provider`|1 (MUST)|String(UTF-8)|Name of the system supplier|
|`System Version`|1 (MUST)|String(UTF-8)|Name of product and version of system|
|`Request Test`|1 (MUST)|Code: {[WHAT CODES?]}|Indicator that system passes data request tests satisfactorily|
|`Response Test`|1 (MUST)|Code: {[WHAT CODES?]}|Indicator that the system responds to requests satisfactorily|
|`API endpoints`|1 (MUST)|Code: {[WHAT CODES?]}|Operational endpoints for data exchange|

<a href="https://github.com/SocialCareData/taxonomy/issues/new?template=content_issue.yml&title=Organisations%20Register:%20" class="web-button" target="_blank">Raise an issue about register of organisations</a>