# OpenADE Task Force Meeting 2026-02-11

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


## NAESB ESPI Standard Proposed Changes for ESPI Version 4.1
* Remove SFTP as a transport option from the ESPI standard
  * The NAESB ESPI Task Force met January 29th and recommended SFTP as a transport protocol be removed from the 
    NAESB ESPI standard.
    * The request (R25005) is currently undergo a 30-day [review and comment](https://naesb.org/retail_request.asp) period until February 27th, 2026.
  
## GBA Technical Resource Sample Code Segments
* During the January 14th meeting the following topics were discussed and agreed by the GBA Staff to provide 
  additional implementation documentation:
    * UUID Generation -- [Generating Persistent UUIDs](https://www.greenbuttonalliance.org/generating-persistent-uuids) has been updated with detail examples and sample implementation logic.

## Additional NAESB ESPI Standard Changes
* Simplify the ESPI Customer schema to reflect the same organization for Customer and IdentifiedObject as exist in 
  the espi.xsd schema.
* Refactor the ESPI standard to reflect elements that are actively supported by utilities.
  * Remove POST, PUT, and DELETE operations for Resource Servers from the ESPI standard.
    * Affects Section REQ.21.6.2.1 ESPI REST API Interface

## Open Discussion
* [Jeremy] Does the addition of a new Interval Length capability by a Data Custodain require a customer to 
  re-authorize a Third Party's current authorization?
* [Kat] Can the ESPI Billing information be used for invoicing?

## Attendees
* Donald F Coffin (Green Button Alliance) (Maintainer)
* Jeremy J. Roberts (Green Button Alliance)
* Dee Hastey (Big Data Energy Services)
* Mike Foye (Paymentus)
* Valdis Hellevik (Green Button Alliance)
* Ekaterina (Kat) Rubin (City of Toronto)
* Daniel Roesler (Daniel Roesler LLC)
* William Kane (Best Energy Power NYC)
* Craig Schreder (Rodan Energy Systems)
* Morgan Harrison (UtilityAPI)
* Gary Cook (Jotson)


## Minutes

## Key takeaways
- The SFTP protocol is being removed from the NASBE standard as no one has certified for it in over a decade
- GBA is developing code samples in multiple languages (prioritizing Python and TypeScript/JavaScript) to help with implementation challenges
- A proposal to simplify the UML diagram for the schema was presented to make resources easier to understand
- A proposal to remove section REQ21.6.2.1 regarding CRUD operations was discussed, as GET is realistically the only operation utilities allow
- Discussion about whether reauthorization is needed when interval data granularity changes (e.g., from monthly to hourly)
- Green Button billing data has limitations in representing exact bill amounts due to rounding issues

## Discussed topics

##  SFTP Protocol Removal
  Donald Coffin provided an update on the removal of SFTP as a transport protocol from the SP standard.
### Details
  - Donald: The SB Task Force met and agreed to strike SFTP as a transport protocol from the SP standard
  - Donald: The change is currently under a 30-day public comment period
  - Donald: If approved, it will be published in the next version of the SB standard (4.1), targeted for May or June 2023
  - Jeremy Roberts: Confirmed the Retail Market Quadrant Executive Committee meeting is in April
 
 
###Conclusion
  - The removal is progressing through the approval process
  - This will be the first publication of the standard in two and a half years
## UUID Management
    Donald and Jeremy presented work on UUID management to help developers.
### Details
  - Donald: Showed example code for generating UUIDs, explaining that UUIDs must be repeatable
  - Donald: The code uses domain as namespace and meter location as constant
  - Jeremy: Mentioned they secured a certificate for "imaginarypowerandlight.com" for examples
  - Donald: Asked for feedback from coders and programmers on the examples


### Conclusion
  - The team will continue developing examples in multiple languages
  - Feedback is requested on what examples would be most helpful next
## UML Diagram Simplification
    Donald presented a proposal to simplify the UML diagram for the schema.
### Details
  - Donald: Current UML diagrams are confusing with resources buried under multiple layers
  - Donald: Proposed changes would make resources directly inherit from identified object
  - Donald: The changes would not impact the XML output format
  - Daniel: Expressed support for the consolidation as it would make navigation easier


### Conclusion
  - The proposal will be submitted as a request
  - The changes will make the schema easier to understand while maintaining compatibility
## CRUD Operations Removal
    Donald proposed removing section REQ21.6.2.1 regarding CRUD operations.
### Details
  - Donald: The standard currently supports all CRUD operations (GET, POST, PUT, DELETE)
  - Donald: Realistically, GET is the only operation utilities allow for third parties
  - Donald: POST exists for dynamic client registration but to the authorization server, not resource server
  - Daniel: Asked for clarification about application information POST, which Donald confirmed is different


### Conclusion
  - The proposal is to remove section 21.6.2.1 for anything that doesn't have a GET operation
  - The POST for registration would be noted as not being a resource endpoint
## Reauthorization for Interval Changes
    Jeremy raised a question about whether reauthorization is needed when interval data granularity changes.
### Details
  - Jeremy: Asked if reauthorization is needed when interval size becomes tighter (e.g., monthly to hourly)
  - Daniel: Suggested it's more of a legal/regulatory question than technical
  - Donald: Explained it depends on whether interval duration was in the original agreed-upon scope
  - Gary: Raised concerns about technical implications for third parties if data granularity changes
  - Daniel: Noted potential calculation issues if applications aren't prepared for more granular data


### Conclusion
  - If interval duration is not defined in the scope, there's more flexibility
  - Regulatory bodies can override standard recommendations
  - Utilities should provide lead time to third parties before changing data granularity
## Green Button Billing Accuracy
    Kat asked about the accuracy of Green Button billing data.
### Details
  - Kat: Asked if Green Button billing data could completely replace traditional invoicing
  - Jeremy: Explained limitations due to rounding (Green Button uses 10^-5 scaling factor)
  - Gary: Noted that in Ontario, some utilities use a multiplier of 2 on dollar amounts, making rounding less of an issue
  - Jeremy: Showed examples where tiny fractions can cause discrepancies between actual bills and Green Button data


### Conclusion
  - Green Button billing data is fairly accurate but has limitations due to rounding
  - Different utilities may use different naming conventions for billing line items
  - A new page on accuracy and quality of reading was recently added to the developer resources
## Action items
### Donald
  [X] Post meeting minutes and notify via OpenAD email and website
  [] Submit proposal to simplify UML diagram
  [] Submit proposal to remove section REQ21.6.2.1
  [] Continue developing the resource and authorization servers for the sandbox
### Donald and Jeremy
  [] Develop the bulk authorization flow
  [] Continue work on TypeScript examples
  [] Share bulk authorization flow with Gary, Kat, and Morgan
### All participants
  [] Review the UUID management page and provide feedback on examples
  [] Suggest what code examples would be most helpful next