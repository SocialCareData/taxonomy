# Describing a `Service Involvement`

There's two parts to this: defining services, and defining a service's involvement with a person. The former would be like organisations (organisations is for data sharers/stewards/accessors, whereas services is for practitioners) and the latter would (potentially) resemble one item in a ledger attached to each person, therefore referenced by a person and referencing a service provider.  

## Describing a `Service`: specification

|Field name|Cardinality|Data Type & Format|Description & Reasoning|Priority|
|----------|-----------|------------------|-----------------------|--------|
|`serviceIdentifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the service.|1|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the service.|1|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|1|
|`serviceName`|1 (MUST)|String(UTF-8)|Name of the service|1|
|`serviceType`|1 (MUST)|Code: {1=Central Government, 2=Local Government, 3=Education, 4=Housing, 5=Health, 6=Social Care, 7=Police, 8=Finance, 0=Unknown}|(primary) Type of the service|1|
|`status`|0, 1 (SHOULD)|Code: {[WHAT CODES?]}|The status of the service provision.|0|
|`Contact`|1 (MUST)|**Object**|Contact details TODO|0|

note: no list of practitioners here


## Describing a `Service Involvement`: specification

|Field name|Cardinality|Data Type & Format|Description & Reasoning|Priority|
|----------|-----------|------------------|-----------------------|--------|
|`involvementIdentifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the specific service involvement.|1|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the specific service involvement.|1|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|1|
|`involvementType`|1 (MUST)|Code: {[WHAT CODES?]}|Nature of the service's involvement or role in the person's social care|0|
|`startDate`|0, 1 (SHOULD)|Date (ISO8601: `YYY-MM-DD`)|The beginning of the service provision. The `YYYY-MM-DD` ISO8601 format is the international standard, utilised by the NHS for date records.|1|
|`endDate`|0, 1 (SHOULD)|Date (ISO8601: `YYY-MM-DD`)|The end of the service provision. The `YYYY-MM-DD` ISO8601 format is the international standard, utilised by the NHS for date records.|1|
|`Practitioners`|1 (MUST)|**Object**|Practitioners involved TODO|0|
|`Further Information`|0 (Should)|**Object**|further info necessary to describe the service involvement TODO|0|

note: this is where we start to combine back with placements standard i think

<a href="https://github.com/SocialCareData/person-standard/issues/new?template=content_issue.yml&title=Services:" class="web-button" target="_blank">Raise an issue about Services and Service Involvements</a>