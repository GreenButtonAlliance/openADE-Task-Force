# OpenADE Task Force Meeting 2023-08-08

## Agenda
* Welcome
* Work on OpenADE Task Force issues:
  * Issue #1 - [#1](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/1)
  * Render - https://www.greenbuttonalliance.org/issue-001
  * Issue #5 - [#5](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/5)
  * Render - https://www.greenbuttonalliance.org/issue-005
* Review and approve minutes

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data ES)
* Daniel Roesler (UtilityAPI
* Sophia Wen (Logical Buildings
* Klaar De Schepper (Flux Tailor)

## Minutes
* Reviewed the recently created GitHub repository for tracking OpenADE Task Force issues, meeting agenda, and minutes
* Welcome and attendance
* Reviewed Issue #1 and discussed the proposed solution
  * Don discussed the current capability to relate a meter to a UsagePoint in the Retail Customer schema
  * Don pointed out the current capability does not provide the ability to link multiple meters at a ServiceLocation to 
    their associated UsagePoint
  * Klaar de Schepper commented that she had discovered this issue as well
  * Don then presented a proposed solution to add a Single UsagePoint to the EndDevice abstract class
    * Since the Meter resource inherits from the EndDevice abstract class, this would allow a single UsagePoint to be 
      associated with a Meter
    * Klaar asked if the solution was a one-to-one relationship between the Meter and the UsagePoint
    * Don confirmed the solution is a one-to-one relationship and the UsagePoint is accessible from the Meter since 
      the contents of the field is a URL which should be the same value as the href= attribute of the UsagePoint's 
      atom rel="self" link
    * Klaar then asked if the proposed solution was redundant since the current ServiceLocation also 
      contains a list of UsagePoints
    * Don confirmed the proposed solution is redundant, but the proposed solution is a more direct way to access the 
      UsagePoint from the Meter
    * Don mentioned the issue was raised by a ThirdParty attempting to digitize a paper billing statement that had 
      several meters 
      for a single ServiceLocation
    * Don also pointed out that the proposed solution would affect the current Retail Customer schema CMD and DMD 
      certification tests
    * Klaar recommended that the proposed solution is a better solution to correlate Meters with their 
      UsagePoint than the current ServiceLocation UsagePoint list since it is more direct and that UsagePoint should 
      be required for all Meter resources.
    * Don then indicated that the current ServiceLocation UsagePoint list could be deprecated in the 3.4 NAESB 
      version and removed in the 3.5 NAESB version.
    * A discussion then occurred about how to represent other types of EndDevices such as street lights.
    * Don and Daniel Roesler pointed out that street lights are defined as 'virtual' meters without an assigned 
      UsagePoint, meter readings, or ServiceLocation.
    * Daniel pointed out street lights are an unmetered service with no interval readings.
    * Daniel commented that he would expect to see a Retail Customer representation for a street light to have a 
      Service Agreement and Service Location, but no UsagePoint or Meter.
    * Klaar asked if each street light is then assigned a ServiceLocation?
    * Don responded that often street lights are not assigned a ServiceLocation.
    * Daniel then asked if there is a tariff for Service Agreements since the service fee is reported in the 
      UsageSummary resource which is associated with the UsagePoint.
    * Daniel then pointed out the requirement for a UsagePoint may create multiple references to the same UsagePoint 
      between the Retail Customer and the Energy Usage Information resources.
    * Klaar then pointed out that UsagePoint is not a thing in the Retail Customer it is merely a reference.
    * Daniel then confirmed he is fine with the proposed solution.
    * Daniel asked if it was possible in the current NAESB REQ.21 ESPI ver 3.3 to add an atom <link> reference to 
      the Retail Customer Meter resource that contained the URL of the UsagePoint as a short-term solution?
    * Don responded that it is possible, and it would have no impact on the current CMD/DMD certification tests.
    * A motion was made by Klaar and seconded by Daniel to submit a NAESB Request to implement the proposed solution.
  
* Reviewed Issue #5 and discussed the proposed Retail Customer Statement resource schema content
  * Reviewed the NAESB PDF Statement Request proposal and GitHub issue comments
  * Klaar mentioned she had spoken with Ben White (Arcadia) who was interested in when the support would be 
    available since they would like to test the capability.
  * Klaar offered to update the Retail Customer schema to include the proposed Statement resource.
  * Don shared the NAESB Request he had completed to add the Billing Statement to the current Retail Customer schema
  * Klaar offered to review and ensure the NAESB Request also included digital billing statements.
  * Don agreed to provide Klaar with the NAESB Request for review and comments.
  * Don then reviewed the process that NAESB will perform upon submission of the NAESB Request.
  * Don then discussed other possible changes to the NAESB REQ.21 ESPI standard
    * The current standard supports GET, POST, PUT, and DELETE REST CRUD operations, but since all existing CMD 
      Certifications only support GET and POST, the PUT and DELETE operations are not supported. 
    * Should a NAESB Request be submitted to remove the POST, PUT and DELETE operations from the NAESB REQ.21 ESPI 
      standard?
  * Don then reviewed the other existing Issues in the GitHub OpenADE-Task-Force repository
    * (Issue #2) Don reviewed that Ontario utilities are required to provide digital billing information to their 
      customers and that the current Retail Customer Certification tests do not test for the presence of digital billing 
      information.
    * (Issue #3) Develop a schema mapping that supports migration between NAESB standards to cover removal of 
      DEPRECATED items
    * (Issue #4) Add support for OAuth 2.0 Public Clients to the NAESB ESPI standard.
    * (Issue #6) Add support for OAuth 2.0 JSON Web Token (JWT) Access Tokens to the NAESB ESPI standard.
      * Daniel commented he is not in favor of adding support for JWT Access Tokens to the NAESB ESPI standard since 
        very few utilities properly validate JWT Access Tokens and felt this should be a very low priority.
      * Don mentioned that OpenID Connect only uses JWT Access Tokens which may be needed for statewide systems
      * Daniel pointed out that the NAESB ESPI standard does not support require OpenID Connect and a JWT should not 
        be the required authorization method.
      * Jeremy J. Roberts asked if OAuth 2.1 required JWT Access Tokens?
      * Don responded that OAuth 2.1 does not require JWT Access Tokens it will require the use of PKCE with the 
        Authorization Code request for public and confidential clients.
      * Don also mentioned the implementation of JWT Access Tokens will impact the current CMD Certification 
        platform significantly.
    * Klaar asked about adding a Tariff Plan ID to the NAESB ESPI standard.
      * Don explained the standard currently supports a Tariff URL which is a link to the tariff plan.
      * Don mentioned that several years ago NREL attempted to create a national database of tariff plans.
      * Klaar mentioned she has been working with NREL on the tariff plan database and would like to have the 
        utilities provide their Tariff ID in the NREL database.
      * Klaar stated she is currently designing a Tariff database for the New York state NYERDA program.
      * Klaar mentioned she could submit her Tariff Plan ID proposal.
        * Don asked her to submit her proposal to the OpenADE Task Force repository.
        * Jeremy asked Klaar if NREL ever finalized how they are obtaining Tariff plans from utilities?
        * Klaar responded that NREL is manually entering the Tariff plans into their database for research purposes 
          after researching the utility's website.

## Closing Discussion
* Consensus to commit this to repo? Yes/No