# OpenADE Task Force Meeting 2025-01-08

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


* Review current Technical Activities
  * ESPI support for EPA Portfolio Manager's Green Power (**pending**)
  * Code Snippets
    * How to report billing dollar amounts in the UsageSummary costAdditionalDetailLastPeriod LineItem structure
      (**pending**)
    * Best Practice settings for access_token and refresh_token expiration (**pending**)
  * CMD Certification Platform Pending Updates
    * [FB_26] Usage Summary Billing Details (**pending**)
    * [FB_71] Retail Customer Billing Statement (**pending**)
    * [FB_58] Retail Customer ServiceLocation Information Update (**pending**)
    * [FB_36] Third Party Dynamic Registration Update (**pending**)
  * What topics should the GBA focus on during 2025?
    * Carbon Accounting 
      * Renewable Energy Certificates
      * Percentage Renewable consumption of Energy
        * [Dan] Discussed the current Ontario Energy Consumption reporting requirements
        * [Dan] They use EPA Portfolio Manager to report consumption for Carbon reporting
        * [Dan] Also referenced the PCP Tool (https://pcptools.org) as another Carbon reporting tool
        * [Ashish] Reported another Ontario company that is reporting 
        * [Dan] Indicated that it would be great if the ESPI standard data could be directly imported into the EPA 
          Portfolio Manager
        * [Don] Discussed what the GBA has been working on to provide tools to convert the ESPI data to meet the EPA 
          Portfolio Manager input format 
        * [Ashish] Commented that it would be helpful if the ESPI standard could include additional Carbon accounting data
        * [Dan] Indicated that it is challenging to get CMD to work with utilities due to the OAuth Access Token 
          requirements
        * [Jeremy] Commented that it can be challenging for individuals to develop a 3rd Party relationship
        * [Ashish] Asked if Dan was obtaining the data directly from the meter of the utility
        * [Jeremy] Clarified that Ashish and Dan were discussing two different methods of obtaining the data.
        * [Don] Commented that the UtilityAPI implementation is front ending the utility and then performing the 3rd 
          Party interface
        * [Dan] Discussed how the UtilityAPI interface works 
        * [Don] Asked Dan to provide him with additional information about the UtilityAPI API he uses
    * EPA Portfolio Manager compatibility


* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Jeremy J. Roberts (Green Button Alliance)
* Valdis Hellevik (GBA)
* Dee Hastey (Big Data Energy Services)
* Dan Gowans (City of Sault Ste. Marie)
* Ashish Goel


## Minutes
* TODO

## Closing Discussion
* Consensus to commit this to repo? Yes/No
