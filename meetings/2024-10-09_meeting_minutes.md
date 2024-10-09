# OpenADE Task Force Meeting 2024-10-09

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


* ESPI support for Green Power (**pending**)
  * Review the current EPA Portfolio Manager Green Power reporting requirements and determine how the current Green Button standard can be updated to assist users to report Green Power data to the EPA Portfolio Manager 


* Code Snippets
  * How to link Customer ServiceLocation meters to their UsagePoints (**pending**)
  * How to report billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
    (**pending**)
  * Best Practice settings for access_token and refresh_token expiration (**pending**)


* CMD Certification Platform Pending Updates
  * [FB_26] Usage Summary Billing Details
    * An optional Function Block to verify the utility is properly reporting digital billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
    * The Function Block will be added to both ESPI version 3.3 and version 4.0 TestSuites
    * Generate XSLT tests for the new Function Block (**pending**)
  * [FB_71] Retail Customer Billing Statement 
    * An optional Function Block to verify the utility is properly reporting retrievable digital billing statements
    * The Function Block will be added to the ESPI version 4.0 TestSuites
      * Should [FB_71] be added to the ESPI version 3.3 TestSuites? 
    * Generate XSLT tests for the new Function Block (**pending**)
  * [FB_58] Retail Customer ServiceLocation Information Update
    * Add a new TestStep to [FB_58] Retail Customer ServiceLocation Information to confirm the utility is properly referencing UsagePoints located at the customer's ServiceLocation
    * Generate XSLT tests for the new TestStep (**pending**)
  * [FB_36] Third Party Dynamic Registration Update
    * [FB_36] was defined to validate utilities properly implemented RFC 7591 and RFC 7592 which allows third parties to dynamically register with the utility
    * Should [FB_36] be made a mandatory Function Block?
  * Should a new Function Block be created that ensures a utility can onboard Third Parties?
    * This Function Block would require the utility to onboard the CMD Certification Platform as a Third Party during the certification process
  * Should the CMD Certification require a utility to prove they are able to onboard Third Parties?


* Frequent Ask Questions GBA website section
  * Should a new FAQ section be added to the GBA website that answers common questions about the Green Button standard?
  * Should the FAQ section be included in the Technical Developer's Resource section or be a separate section?
  * What questions should be included in the FAQ section?


* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Jeremy J. Roberts (GBA)
* Valdis Hellevik (GBA)
* Dee Hastey (Big Data Energy Services)
* Alberto Colombo (DERnetSoft)
* Gavin Hatfield (DERnetSoft)
* Nicole Sullivan (Cleartrace)


## Minutes
* [Don] Welcome and introduction of new attendees
* [Don] Reviewed the minutes of the last meeting
* [Don] Reviewed the status of the EPA Portfolio Manager Green Power reporting requirements
* [Don] Discussed the pending code snippets
* [Don] Discussed the [FB_26] Usage Summary Billing Details updates
* [Don] Discussed the [FB_71] Retail Customer Billing Statement updates
  * [Jeremy] Mentioned that [FB_71] will usually be PDF data files
  * [Jeremy] Further discussed the TLS 1.3 issue and the addition of [FB_71] to the ESPI version 3.3 TestSuites
* [Don] Further discussed the [FB_58] Retail Customer ServiceLocation Information Update
* [Don] Discussed the addition of a FAQ section to the GBA website
  * [Dee] Commented she'd look into here old emails and provide some questions for the FAQ section
  * [Jeremy] Mentioned that we also want to add DER and Carbon Accounting capabilities to the Green Button standard
  * [Nicole] Mentioned she would look into the EPA Portfolio Manager Green Power reporting requirements and provide some feedback
  * [Alberto] Asked how DERs would use the Green Button standard for behind the meter data
    * [Jeremy] Responded how some DERs are using the Green Button standard for behind the meter data and what could be done to improve it
    * [Valdis] Mentioned that London Hydro and Electron did a pilot project with DERs and the Green Button standard a few 
    years ago
    * [Valdis] Offered to provide the report to Alberto



## Closing Discussion
* Consensus to commit this to repo? Yes
