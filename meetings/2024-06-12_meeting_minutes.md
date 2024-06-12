# OpenADE Task Force Meeting 2024-06-12

## Agenda
* Welcome
* Introductions of attendees
* Review and approve minutes

* Code Snippets
    * How to link Customer ServiceLocation meters to their UsagePoints
    * How to report billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
    * Best Practice settings for access_token and refresh_token expiration
* CMD Certification Platform Update
    * All GET Resource URI TestSteps are being refactored to support "200 OK" and "202 Accepted" status code responses
        * "200 OK" status code responses are used for synchronous operations
        * "202 Accepted" status code responses are used for asynchronous operations
            * The CMD Certification Platform will wait for the Third Party Notification Endpoint to receive a BatchList 
              message and then complete the GET Resource URI TestStep using the contents of the "resource" element 
    * Add a new optional Function Block to verify the utility is properly reporting digital billing dollar amounts 
      in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
    * Add a new optional Function Block to verify the utility is properly reporting retrievable digital billing 
      statements
    * Add a new TestStep to [FB_58] Retail Customer ServiceLocation Information to confirm the utility is properly 
      referencing 
      UsagePoints located at the customer's ServiceLocation 

* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Valdis Hellevik (Green Button Alliance)
* Dee Hastey (Big Data Energy Services)
* Daniel Roesler (UtilityAPI)

## Minutes
* [Don] Discussed the Code Snippet changes
    * [Don] Discussed that the GBA will be recommending access_token expiration of 1 hour and refresh_token 
      expiration of 7 days to ensure any network outages do not cause third party applications to lose access.
    * [Daniel] Discussed a network delivery failure issue that caused the third party to not received the issued 
      access token and the refresh_token and therefore unable to access the utility's API
* [Dee] Indicated that only one of the BDES utilities have refresh_token expiration set at 24 hours
* CMD Certification Platform Update
    * [Don] Discussed the CMD Certification Platform Updates
        * [Don] Discussed the refactoring of the GET Resource URI TestSteps to support "200 OK" and "202 Accepted" 
          status code responses
        * [Don] Discussed the new optional Function Blocks to verify the utility is properly reporting digital 
          billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
        * [Don] Discussed the new optional Function Blocks to verify the utility is properly reporting retrievable 
          digital billing statements
        * [Don] Discussed the new TestStep to [FB_58] Retail Customer ServiceLocation Information to confirm the 
          utility is properly referencing UsagePoints located at the customer's ServiceLocation
        * [Don] Also discussed that a new TestStep will be added to ensure that IntervalBlock data is not only 
          report "0" values

## Closing Discussion
* Consensus to commit this to repo? Yes
