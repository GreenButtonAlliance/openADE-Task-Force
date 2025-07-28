# OpenADE Task Force Meeting 2025-03-12

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


* Review current Technical Activities
  * Code Snippets and Developer Resources
    * Best Practice settings for access_token and refresh_token expiration (**pending**)
    * Onboarding Third Party applications (**pending**)
  * CMD Certification Platform Pending Updates
    * [FB_26] Usage Summary Billing Details (**pending**)
    * [FB_71] Retail Customer Billing Statement (**pending**)
    * [FB_58] Retail Customer ServiceLocation Information Update (**pending**)
    * [FB_36] Third Party Dynamic Registration Update (**pending**)
  * 2025 Projects
    * Determine how ESPI can best support the EPA Portfolio Manager's API interface
    * Determine how ESPI can best support Carbon Accounting requirements
      * What values are needed for reporting?
        * Buildings reporting to their states/provinces/localities* 
    * Does provenance matter in reporting
      * Type of energy generation and location
    * Is reporting of Renewable Energy Certificates a requirement
    * Upgrade the GBA Sandbox to comply with current ESPI standards
      * [Gary] Indicated have an open-source Client written in a SPA programming language would have been beneficial
        * [Gary] Especially to handle the OAuth 2.0 process


* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Jeremy J. Roberts (Green Button Alliance)
* Valdis Hellevik (Green Button Alliance)
* Gary Cook (Jotson)
* Mike Foye (Paymentus)


## Minutes
* [Don] Welcome and introduction of new attendees
* [Don] Reviewed the minutes of the last meeting
* [Don] Reviewed the status of the Code Snippets and Developer Resources
* [Don] Reviewed the pending changes in the CMD Certification Platform
  * [FB_26] Usage Summary Billing Details (**pending**)
    * [Gary] Indicated that having billing images would be wonderful
      * [Jeremy] Indicated that Ontario uses Ver 3.3 and the billing image is part of Version 4.0
    * [FB_36] Third Party Dynamic Registration Update (**pending**)
      * [Gary] Commented he just finished update Jotson with all 56 Ontario Utilities
        * [Gary] It took several months to complete the process with the utilities
        * [Gary] Indicated the UtilityAPI has the best onboarding process
        * [Gary] Indicated that only one service provider required a certificate as part of the onboarding process
      * [Jeremy] Asked if we knew if utilities checked Third Party Certificates
        * [Don] Indicated GBA has no way to verify utilities are checking certificates
      * [Valdis] Asked if the GBA could do a write-up on Jotson's onboarding experience
* [Don] Reviewed the 2025 Projects
  * [Don] Discussed the ability for ESPI to provide the EPA Manager additional information beyond metered data
  * [Don] Asked what values are required for Carbon Accounting requirements
    * [Gary] Indicated Jotson is doing Carbon consumption reporting
      * [Jeremy] Asked what measurement Jotson is using for Carbon consumption
        * [Gary] Indicated Jotson is using tons of CO2
  * [Don] Asked if the GBA Sandbox should be upgraded to comply with current ESPI standards
    * [Gary] Indicated that having an open-source Client written in a SPA programming language would have been beneficial
      * [Gary] Especially to handle the OAuth 2.0 process

## Closing Discussion
* Consensus to commit this to repo? Yes/No
