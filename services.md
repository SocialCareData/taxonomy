# Describing a `Service Involvement`: Specification

|Field name|Cardinality|Data Type & Format|Description & Reasoning|
|----------|-----------|------------------|-----------------------|
|`serviceIdentifier`|1, Many (MUST)|**Object**|Unique identifiers (IDs) associated with the service.|
|↳ `Identifier Value`|1 (MUST)|String(UTF-8)|A single unique identifier attached to the service.|
|↳ `Identifier System`|1 (MUST)|URI|A link to the system that the identifier adheres to.|
|`serviceName`|1 (MUST)|String(UTF-8)|Name of the service|
|`serviceType`|1 (MUST)|Code: {[WHAT CODES?]}|Type of the service|
|`involvementType`|1 (MUST)|Code: {[WHAT CODES?]}|Nature of the service's involvement or role in the person's social care|
|`startDate`|0, 1 (SHOULD)|Date (ISO8601: `YYY-MM-DD`)|The beginning of the service provision. The `YYYY-MM-DD` ISO8601 format is the international standard, utilised by the NHS for date records.|
|`endDate`|0, 1 (SHOULD)|Date (ISO8601: `YYY-MM-DD`)|The end of the service provision. The `YYYY-MM-DD` ISO8601 format is the international standard, utilised by the NHS for date records.|
|`status`|0, 1 (SHOULD)|Code: {[WHAT CODES?]}|The status of the service provision.|
|`Practitioners`|1 (MUST)|**Object**|Practitioners involved TODO|
|`Contact`|1 (MUST)|**Object**|Contact details TODO|

<a href="https://github.com/SocialCareData/person-standard/issues/new?template=content_issue.yml&title=Services:" class="web-button" target="_blank">Raise an issue about Services and Service Involvements</a>