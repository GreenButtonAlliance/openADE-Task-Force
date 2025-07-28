# OpenADE Task Force Meeting 2025-05-22

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


* Review current Technical Activities
  * CMD Certification Platform Pending Updates
    * [FB_58] Retail Customer ServiceLocation Information Update (currently being updated)
      * ServiceLocation Resource UsagePoint entries are validated to ensure they contain valid URLs

* Technical Topic
  * How can ESPI report Aggregated Data
    * Aggregated Data is summarized or combined data from multiple sources.
    * Typically used to provide a high-level overview or summary of data trends.
    * Collected from multiple sources and combined into a single dataset.
      * Households, businesses, or other entities
    * The ESPI UsagePoint isVirtual element can be used to indicate the UsagePoint is a virtual point
      *  If true, indicates no physical meter is associated with the UsagePoint
        * Allows a UsagePoint to be defined as an aggregation of usage for multiple physical meters


* Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data Energy Services)
* Walt Hillis (NISC)
* Gary Cook (Josten)
* Valdis Hellevik (Green Button Alliance)
* Klar de Schepper (Flux Taylor)
* Jeremy J Roberts (Green Button Alliance)


## Minutes
* [Don] Opened the meeting and welcomed attendees. Noted missed meeting last month.
* [Attendees] Introductions made by Dee Hastey, Walt Hillis, Gary Cook, Valdis Hellevik, and others.
* [Don] Discussed changes to Function Block 58 to validate absolute HTTPS URLs in UsagePoint entries and how this ensures data integrity.
* [Don] Provided clarification that ESPI already supports aggregated data using `roleFlags` and `isVirtual` fields.
* [Gary] Shared that Jotson is not pursuing aggregated data but noted interest in how it may be useful to others.
* [Claire] Highlighted importance of tariff data and mapping from usage points to premises for cost modeling and benchmarking, referencing Con Edison’s approach.
* [Discussion] Focused on privacy implications, valid schema usage, and need for clearer guidance and examples in the standard.
* [Don] Mentioned plans to publish technical articles to address misunderstandings about the standard’s capabilities.
* [Valdis] Shared that Ontario Ministry of Energy contacted them after reviewing recent GBA presentations.
* [Gary] Described ongoing issues with Ontario utility data availability, including formal complaints to regulatory boards.
* [Don] Requested Gary share utility-specific technical issues to help improve certification tests and documentation.
* [Don] Concluded meeting and reminded attendees that technical support is available to GBA members and the public on a paid basis.
