# OpenADE Task Force Meeting 2024-12-04

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


* Review current Technical Activities
  * ESPI support for EPA Portfolio Manager's Green Power (**pending**)
  * Code Snippets
    * How to link Customer ServiceLocation meters to their UsagePoints (https://www.greenbuttonalliance.org/usagepoint-location)
    * How to report billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
      (**pending**)
    * Best Practice settings for access_token and refresh_token expiration (**pending**)
  * CMD Certification Platform Pending Updates
    * [FB_26] Usage Summary Billing Details (**pending**)
    * [FB_71] Retail Customer Billing Statement (**pending**)
    * [FB_58] Retail Customer ServiceLocation Information Update (**pending**)
    * [FB_36] Third Party Dynamic Registration Update (**pending**)
      * Should the CMD Certification require a utility to prove they are able to onboard Third Parties?
      * Should a new Function Block be created that ensures a utility can onboard Third Parties?

* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Jeremy J. Roberts (Green Button Alliance)
* Parker Brant (Big Data Energy Service)
* Mike Foye (Paymentus)
* Alberto Colombo (DERNetSoft)
* Klaar de Schepper (Flux Taylor)


## Minutes
* [Don] Welcome and introduction of new attendees
* [Don] Reviewed the minutes of the last meeting
* [Don] Discussed the current status of the EPA Portfolio Manager Green Power requirements
  * [Klaar] Asked if we are considering adding all greenhouse gases to the ESPI commodity schema enumerations
  * [Don] Asked Klaar to provide a link to the European publicly available version of the greenhouse gases
    * https://ontology.tno.nl/IEC_CIM/cim_CommodityKind.html
* [Alberto] Asked if we are familiar with WattTime
  * [Alberto] Indicated Watt Power provides the actual consumption not percentage of consumption
  * [Klaar] Indicated WattTime provides an estimate not actual consumption
  * [Don] Reviewed the status of the Code Snippets projects
    * [Don] Reported the UsagePoint <--> ServiceLocation mapping snippet has been posted
  * [Don] Reviewed the pending updates to the CMD Certification Platform
  * [Jeremy] Reviewed the fact ESPI 4.0 requires TLS 1.3 only
    * [Jeremy] Asked if the GBA should support Digital Billing Images if the utility still supports TLS 1.2 
      * [Klaar] Responded that Digital Billing images should be supported with a commitment by the utility will 
        support only TLS 1.3 in the future
  * [Jeremy] Asked attendees if they thought having a SDK to retrieve Green Button data would be helpful
    * [Mike] Responded he has several projects going and is looking for help
      * [Klaar] Asked Mike if he was a competitor to FiServ and provided recommendations on how to get help
    * [Alberto] Agreed with Klaar's comments
  * [Jeremy] Mentioned the GBA AGM on December 11th and reminded everyone to register

## Closing Discussion
* Consensus to commit this to repo? Yes/No
