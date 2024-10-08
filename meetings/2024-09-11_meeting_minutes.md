# OpenADE Task Force Meeting 2024-09-11

## Agenda
* Welcome
* Introductions of attendees
* Review and approve minutes


* EPA Portfolio Manager
  *  The Green Button supports data that is useful for reporting data to the EPA Portfolio Manager
  * The EPA Portfolio Manager supports Green Power reporting
    * Green Power supports REC purchases which identifies the type of energy purchased
    * The EPA Portfolio Manager reports Green Power at the property and meter level
    * We need to review the current EPA Portfolio Manager Green Power reporting requirements and determine how the current Green Button standard can be updated to assist users to report Green Power data to the EPA Portfolio Manager


* NAESB ESPI Standard Updates
  * Source-of-Energy reporting
  * Carbon Accounting


* EPA Portfolio Manager reporting requirements 
  * Review the current EPA Portfolio Manager Green Power reporting requirements and determine how the current Green Button standard can be updated to assist users to report Green Power data to the EPA Portfolio Manager 


* Code Snippets
  * How to link Customer ServiceLocation meters to their UsagePoints (**pending**)
  * How to report billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
    (**pending**)
  * Best Practice settings for access_token and refresh_token expiration (**pending**)


* CMD Certification Platform Pending Updates
  * Add a new optional Function Block to verify the utility is properly reporting digital billing dollar amounts
    in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
    * What should the Energy Usage Function Block be named?
    * Should the new Function Block be added to the Version 3.3 and the Version 4.0 TestSuites?
  * Add a new optional Function Block to verify the utility is properly reporting retrievable digital billing
    statements
    * What should the Retail Customer Function Block be named?
    * Should the new Function Block be added to the Version 3.3 and the Version 4.0 TestSuites?
      * If added to the Version 3.3 TestSuites should the CMD Certification Platform be renamed to not follow
        the NAESB naming convention?
        * Since the NAESB ESPI version 4.0 standard requires only TLS 1.3, utilities with cloud frontends that
          support TLS 1.2 and TLS 1.3 fail the [FB_13] Energy Usage Security and Privacy and [FB_64]
          Retail Customer Security and Privacy Test that want to support Digital Statements
  * Add a new TestStep to [FB_58] Retail Customer ServiceLocation Information to confirm the utility is properly
    referencing UsagePoints located at the customer's ServiceLocation
  * Should [FB_36] Third Party Dynamic Registration be made a mandatory Function Block
    * [FB_36] was defined for the original CMD Certification Platform as an optional Function Block
    * Making it a mandatory Function Block will require all utilities to support the "OAuth 2.0 Dynamic Client
      Registration Protocol" [RFC 7591] and the "OAuth 2.0 Dynamic Client Registration Management Protocol" [RFC 7592]
      to be certified


* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Jeremy J. Roberts (Green Button Alliance)
* Dee Hastey (Big Data Energy Services)
* Valdis Hellevik (Green Button Alliance)
* Ashish Goel (Sanalife)

## Minutes
* [Don] Welcome and introduction of new attendees
* [Don] Reviewed the minutes of the last meeting
* [Don] Discussed the similarity between Green Button and the EPA Portfolio Manager
  * [Jeremy] Feels the OpenADE Task Force can support Green Power reporting if we can obtain experts in the EAC and REC markets.
  * [Dee] Discussed her role in supporting the EAC and REC markets for BDES.
* [Don] Discussed the status of the pending Code Snippets 
* [Don] Discussed the status of the CMD Certification Platform updates 
  * [Dee] Discussed issues with onboarding with new utilities 

## Closing Discussion
* Consensus to commit this to repo? Yes
