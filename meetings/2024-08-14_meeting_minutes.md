# OpenADE Task Force Meeting 2024-08-14

## Agenda
* Welcome
* Introductions of attendees
* Review and approve minutes


* Code Snippets
    * How to link Customer ServiceLocation meters to their UsagePoints (**pending**)
    * How to report billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure 
      (pending)
    * Best Practice settings for access_token and refresh_token expiration (**pending**)


* CMD Certification Platform Completed Updates
    * All GET Resource URI TestSteps are being refactored to support "200 OK", "202 Accepted", "400 Bad Request", 
      and "403 Forbidden" 
      status code responses
        * "200 OK" status code responses are used for synchronous operations
        * "202 Accepted" status code responses are used for asynchronous operations
            * The CMD Certification Platform will wait for the Third Party Notification Endpoint to receive a BatchList 
              message and then complete the GET Resource URI TestStep using the contents of the "resource" element
        * "400 Bad Request" status code responses are used for invalid requests
            * The CMD Certification Platform will verify the response contains "An unprocessed batch request for the 
              same resource already exists" and treat the status code as a "202 Accepted" response.
        * "403 Forbidden" status code responses are used for unauthorized requests
            * The CMD Certification Platform will perform an OAuth 2.0 "Refresh Token" flow and then retry the request. 
        * All SoapUI Templated GET Resource URI requests have been refactored to use the same SoapUI TestCase in the 
          Library TestSuite 
  * All GET Authorization URI TestSteps are being refactored to support "200 OK", "202 Accepted", "400 Bad Request",
    and "403 Forbidden"
    status code responses
      * "200 OK" status code responses are used for synchronous operations
      * "202 Accepted" status code responses are used for asynchronous operations
          * The CMD Certification Platform will wait for the Third Party Notification Endpoint to receive a BatchList
            message and then complete the GET Resource URI TestStep using the contents of the "resource" element
      * "400 Bad Request" status code responses are used for invalid requests
          * The CMD Certification Platform will verify the response contains "An unprocessed batch request for the
            same resource already exists" and treat the status code as a "202 Accepted" response.
      * "403 Forbidden" status code responses are used for unauthorized requests
          * The CMD Certification Platform will perform an OAuth 2.0 "Client Credential" flow and then retry the 
            request.
      * All SoapUI Templated GET Resource URI requests have been refactored to use the same SoapUI TestCase in the
        Library TestSuite
  *  [FB_31] Energy Usage Authorization and Authentication w/o Pre-Negotiated Scope TestSuite OAD013 [NEG]
     (old A) Valid refresh_token request invalidates prior access_token TestCase has been deleted
      * The purpose of the OAD013 TestCase was to verify that after an OAuth 2.0 "Refresh Token" flow that any 
        existing access token was no longer valid
      * The "OAuth 2.0 Authorization Framework" [RFC 6749] allows multiple access tokens to be valid, and although 
        it requires any existing refresh_token to be invalid after the "Refresh Token" flow it allows any existing 
        access token to be valid until it expires
      * Since the OAuth 2.0 standard does not require existing access tokens to expire when a "Refresh Token" flow 
        is performed, the OAD013 TestCase is not valid and has been removed~
  *  [FB_65] Energy Usage Authorization and Authentication w/o Pre-Negotiated Scope TestSuite OAD033 [NEG]
     (old A) Valid refresh_token request invalidates prior access_token TestCase has been deleted
      * The purpose of the OAD013 TestCase was to verify that after an OAuth 2.0 "Refresh Token" flow that any
        existing access token was no longer valid
      * The "OAuth 2.0 Authorization Framework" [RFC 6749] allows multiple access tokens to be valid, and although
        it requires any existing refresh_token to be invalid after the "Refresh Token" flow it allows any existing
        access token to be valid until it expires
      * Since the OAuth 2.0 standard does not require existing access tokens to expire when a "Refresh Token" flow 
      * is performed, the OAD013 TestCase is not valid and has been removed (**COMPLETED**)~ 


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


* NAESB ESPI Standard Updates
    * Source-of-Energy reporting
    * Carbon Accounting


* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data Energy Services)
* Yogesh Moradiya (BES - Ontario, Canada)
* Valdis Hellevik (Green Button Alliance)
* Daniel Roesler (UtilityAPI)

## Minutes
* Welcome and introduction of new attendees
* [Don] Reviewed the status of the Code Snippets being added to the GBA website
* [Don] Reviewed the status of the CMD Certification Platform updates
* [Don] Reviewed the status of the CMD Certification Platform pending updates
  * Add a Function Block to verify contents of the costAdditionalPeriod LineItem structure 
    * [Daniel] Suggested the digital billing LineItem FB be called "Detailed Cost Usage Summary with Billing Information"
    * [Don] Recommended the new FB be added to the Version 3.3 and Version 4.0 TestSuites
  * Add a Function Block to verify the contents of the Retail Customer Statement Resource
    * [Don] Suggested the new FB be named "Retail Customer Billing Statement"
    * [Don] Recommended it be added to Version 4.0 of the CMD Certification Platform
    * [Don] Recommended it also be added to the Version 3.x TestSuites
      *  This allows implementations that certify to the ESPI 3.3 standard to also support the Retail Customer 
         Statement Resource
    * [Daniel] Asked for clarification on whether ESPI ver 4.0 requires only TLS 1.3
      * [Don] Confirmed that ESPI ver 4.0 requires only TLS 1.3 
    * [Daniel] Recommended a utility should be able to apply for ESPI 3.3, ESPI 4.0, or a ESPI 3.3 with ESPI 4.0 Retail 
      Customer Statement Resource
    * [Daniel] Recommended the GBA Board reconsider the requirement that a utility must certify to the latest 
      version of the NAESB ESPI standard
* [Don] Discussed NAESB ESPI Standard Updates
    * Source-of-Energy reporting
       * [Don] Discussed adding Source of Energy to the IntervalReading similar to the EPA Portfolio Manager 
         reporting structure
    * Carbon Accounting

## Closing Discussion
* Consensus to commit this to repo? Yes/No
