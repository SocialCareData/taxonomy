# Describing a `Service Involvement`

There's two parts to this: defining service providers, and defining a service provider's involvement with a person. The former would be like organisations (organisations is for data sharers/stewards/accessors, whereas services is for practitioners) and the latter would (potentially) resemble one item in a ledger attached to each person, therefore referenced by a person and referencing a service provider.  

## Describing a `Service Provider`: specification

|Field name|Cardinality|Data Type & Format|Description & Reasoning|
|----------|-----------|------------------|-----------------------|
|`serviceIdentifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the service.|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the service.|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|
|`serviceName`|1 (MUST)|String(UTF-8)|Name of the service|
|`serviceType`|1 (MUST)|Code: {[WHAT CODES?]}|Type of the service|
|`status`|0, 1 (SHOULD)|Code: {[WHAT CODES?]}|The status of the service provision.|
|`Contact`|1 (MUST)|**Object**|Contact details TODO|

note: no list of practitioners here


## Describing a `Service Involvement`: specification

|Field name|Cardinality|Data Type & Format|Description & Reasoning|
|----------|-----------|------------------|-----------------------|
|`involvementIdentifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the specific service involvement.|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the specific service involvement.|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|
|`involvementType`|1 (MUST)|Code: {[WHAT CODES?]}|Nature of the service's involvement or role in the person's social care|
|`startDate`|0, 1 (SHOULD)|Date (ISO8601: `YYY-MM-DD`)|The beginning of the service provision. The `YYYY-MM-DD` ISO8601 format is the international standard, utilised by the NHS for date records.|
|`endDate`|0, 1 (SHOULD)|Date (ISO8601: `YYY-MM-DD`)|The end of the service provision. The `YYYY-MM-DD` ISO8601 format is the international standard, utilised by the NHS for date records.|
|`Practitioners`|1 (MUST)|**Object**|Practitioners involved TODO|
|`Further Information`|0 (Should)|**Object**|further info necessary to describe the service involvement TODO|

note: this is where we start to combine back with placements standard i think

<a href="https://github.com/SocialCareData/person-standard/issues/new?template=content_issue.yml&title=Services:" class="web-button" target="_blank">Raise an issue about Services and Service Involvements</a>