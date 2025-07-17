## Purpose

This repository provides a simple taxonomy for organising, classifying and describing key concepts in Children’s Social Care.

## Scope

The initial scope is limited to those concepts needed to support the Multi Agency Data Sharing (MAIS) use case (e.g. Family Context).

For version 0.1, we propose this scope is limited to:

- Organisations
- Persons
- Services
- Service involvements
- Roles and relationships (e.g. being in receipt of care)
- Data Processing Agreements (Information Governance)

## Example

As an example, in the context of a single view system:
- We need to be able to describe and catalog organisations and service providers, so that we can direct requests for information. 
- We need to be able to refer to service involvements (e.g. tell me about Harry's service involvements), which requires an ability to talk about services. 
- We need to be able to talk about professionals (a role played by a person) and their relationship to a service involvement. 
- We need to be able to refer to Data Processing Agreements and to specific agreed data sharing use cases which they authorise. 

Bringing all this together we are then able to consistently and coherently say: 

"This is a request from organisation 1, to organisation 2, for information about any service involvements and related professionals for this person, and it is made under the aegis of use case 1 within DPA1"

## Context
Social Finance, the Open Data Institute and Coram are working in partnership to develop data and interoperability standards for Children's Social Care. This work is funded by the Department for Education (DfE) as a part of the manifesto commitment to establish a Single Unique Identifier and secure its benefits for vulnerable children and young people.

This creation of these standards aims to make it easier for data created in one system to be accessed in another, and to be meaningful in another. It aims to deliver:  
- Improved safeguarding – with social workers in more LAs able to look up information in partners’ systems.  
- Improved analysis – by making it easier to analyse the interaction of different services. E.g. for understanding the impact of timely CAMHS provision (or its absence) on children’s journeys into care.  
- Reduced administration – with productivity-enhancing tools for social workers more easily able to integrate with Case Management Systems (CMS), and routine exchange and recording of notifications now easier to automate.  
  

We also plan to use the opportunity of developing national standards to normalise approaches to data sharing which implement privacy by design and by default.    

This work is being delivered in close coordination with the Department for Health and Social Care (DHSC) given the important overlaps with adult social care, and under the direction of a steering board which brings together a range of stakeholders.

<a href="https://github.com/SocialCareData/taxonomy/issues/new?template=content_issue.yml&title=Context:%20" class="web-button" target="_blank">Raise an issue about Context</a>

## Guiding principles
1. **Privacy By Design**: The data specifications must be developed to allow controlled access to data preserving privacy by default. 
2. **Security By Design**: The specifications must ensure information flow between parties adheres to security and confidentiality best practices. 
3. **Unambiguous Personal Data Representation**: The data specifications must enable the unambiguous identification of individuals and ensure that data about a person is always accurately linked to the person. 
4. **Enabling Quality Data**: The data specifications must define clear expectations for data types, formats, and permissible values, enabling systems to generate, exchange, and consume high-quality, reliable information that is fit for its intended purpose. 
5. **Collaborative Data Exchange**: The data specifications must promote seamless interoperability and collaborative data sharing among stakeholders. 
6. **Simplicity**: The data specifications must prioritise ease of understanding and implementation. Complexity should only be introduced when to address specific professional or regulatory requirements. 
7. **Reuse Existing Standards**: Where possible, specifications should align with UK implementations of HL7 FHIR, an established international standard widely used in health systems and increasingly in social care. We will align with FHIR unless: 
    - It affects our ability to deliver the use case 
    - The burden of change (for suppliers) is too great. 
    - Counterparties are unable to adopt it. 
    - There is a prescribed government standard. 
In which case, we will aim to select from another, established data standard in the fields of health and social care, before resorting to defining new standards. 
8. **Develop Standards in the Open**: Encourage check and challenge from suppliers, the sector and others. 

<a href="https://github.com/SocialCareData/taxonomy/issues/new?template=content_issue.yml&title=Principles:%20" class="web-button" target="_blank">Raise an issue about Guiding Principles</a>
