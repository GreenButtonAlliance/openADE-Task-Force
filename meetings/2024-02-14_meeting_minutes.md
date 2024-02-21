# OpenADE Task Force Meeting 2024-02-14

## Agenda
* Welcome
* Review and approve minutes

* Review results of the [OpenADE Task Force Survey](https://www.greenbuttonalliance.org/technical-committee)
    * Enhancements to the ESPI Standard
        * 40% - High Priority
        * 10% - Medium Priority
        * 20% - Low Priority
        * 30% - No Interest/Need
    * Integration with other standards and technologies
        * 10% - Immediate Priority
        * 60% - High Priority
        * 10% - Medium Priority
        * 20% - No Interest/Need
    * Sandbox Tools for Third Party Developers
        * 20% - Immediate Priority
        * 30% - High Priority
        * 50% - Medium Priority
    * Sandbox Tools for Utility Developers
        * 10% - Immediate Priority
        * 20% - High Priority
        * 30% - Medium Priority
        * 40% - Low Priority
    * Example code and snippets to understand the standard
        * 40% - Immediate Priority
        * 20% - High Priority
        * 20% - Medium Priority
        * 20% - No Interest/Need
    * Certification Rules for Third Party Applications
        * 20% - Immediate Priority
        * 30% - High Priority
        * 20% - Medium Priority
        * 30% - No Interest/Need
    * Enhancements to the Certification Rules for Utility Applications
        * 20% - Immediate Priority
        * 30% - High Priority
        * 10% - Medium Priority
        * 20% - Low Priority
        * 20% - No Interest/Need
    * Highest Immediate Priority 40% -- Example code and snippets to understand the standard
    * Highest High Priority 60% -- Integration with other standards and technologies
    * Highest Medium Priority 30% -- Sandbox Tools for Third Party Developers
    * Highest Low Priority 40% -- Enhancements to the Certification Rules for Utility Applications
    * Highest Immediate + High Priority
        * 70% -- Integration with other standards and technologies
        * 60% -- Example code and snippets to understand the standard
        * 50% -- Sandbox Tools for Third Party Developers
        * 50% -- Certification Rules for Third Party Applications
        * 50% -- Enhancements to the Certification Rules for Utility Applications
        * 50% -- Enhancements to the ESPI Standard
        * 40% -- Sandbox Tools for Utility Developers

* What standards and technologies should be integrated with ESPI?

* What example code and snippets would be most helpful to understand the ESPI standard?

* How should the group of 50% be prioritized?

* Work on OpenADE Task Force issues:
    * Issue #5 -- Retail Customer Statement Resource Update - [#5](https://github.
      com/GreenButtonAlliance/openADE-Task-Force/issues/5)
    * Render - https://www.greenbuttonalliance.org/issue-005
        * Published in the NAESB REQ.21 ESPI ver. 4.0 standard

    * Issue #1 -- Correlation of Multiple UsagePoints for a ServiceLocation - [#1](https://github.
      com/GreenButtonAlliance/openADE-Task-Force/issues/1)
    * Render - https://www.greenbuttonalliance.org/issue-001
        * NAESB Corrective Request pending submission

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data Energy Services)
* Dan Gowans (City of Sault Ste. Marie)
* Sasa (London Hydro)
* Aman (London Hydro)
* Valdis Hellevik (Green Button Alliance)
* Luke Scheidler (Itron)

## Minutes
* Welcome
* Review prior meeting minutes
    * [Don] Minutes from the November 2023 meeting were lost due to transferring to a new computer
* Review results of the OpenADE Task Force Survey
    * Results of the survey showed the highest interest was in integration of the ESPI standard with other standards and technologies and example code and snippets to understand the ESPI standard 
    * The lowest interest was Sandbox Tools for Utility Developers
* Discuss what standards and technologies should be integrated with ESPI
    * [Luke] Metered DI data elements (e.g., streaming data and load disaggregation data) enhancements technology
    * [Dee] There is no standard OAuth 2.0 implementation, everyone does it differently
        * [Dee] Both certified and non-certified utilities are using OAuth 2.0 differently
            * [Don] The GBA can only focus on certified utilities
                * [Don] Mentioned there are several OAuth 2.0 RFCs that are not covered by the NAESB REQ.21 ESPI standard
                * [Don] Referenced the PKCE (PKCE for OAuth 2.0) [RFC 7636] as an example of an OAuth 2.0 RFC not covered by the NAESB REQ.21 ESPI standard
                * [Don] Also referenced the JSON Web Tokens for OAuth 2.0 [RFC 7519] as an example of an OAuth 2.0 RFC not covered by the NAESB REQ.21 ESPI standard
                * [Don] Mentioned that not all commercially available Authorization Server support the OAuth 2.0 [RFC 6749] optional Authorization Code flow elements
        * [Dan] Also said he has seen differences between two of the utilities he has onboarded with in Ontario
            * [Dan] Stated that he uses an API token and does not need a scope string to access GB data from an Ontario utility
                * A discussion then ensued about the differences between OAuth 2.0 and API tokens
    * [Dan] Standards for third-party onboarding with utilities
    * [Dan] Stated he is working on a report that will allow the city Energy Manager to compare aggregated GB 
      data and the Energy Star Portfolio Manager (ESPM) integration
* Discuss what example code and snippets would be most helpful to understand the ESPI standard
    * [Don] Discussed existing code snippets (i.e., powerOfTenMultiplier Usage) on the GBA Website
    * [Dee] Not all utilities implement NameSpaces using the same coding technique
    * [Dan] What is the code flow a third party developer needs to use to obtain an access token?
       * [Dan] What portions of the access token response should the third party developer save?
    * [Luke -- after the meeting] Retail Customer revokes consent for a specific meter data stream
    * [Luke -- after the meeting] Retail Customer revokes consent for a sub meter data stream
    * [Luke -- after the meeting] Retail Customer moves out
    * [Luke -- after the meeting] Retail Customer moves out and then in to another service location
    * [Luke -- after the meeting] Utility "swaps" meter
    * [Luke -- after the meeting] Utility "removes" meter (i.e., there is no meter at the location)
    * [Dee -- after the meeting] How should a Utility developer revoke an access token?
    * [Dee -- after the meeting] How should a third party developer revoke an access token?
* Discuss how to prioritize the group of 50% topics
    * [Dee] Suggested Certification Rules for Third Party Applications should be the highest priority of the 50% group
        * Discussion of what Third Party Application Certification Rules for certification should be?
            * [Jeremy] Asked for guidance on what types of things does the GBA third party certification need to cover?
                * [Jeremy] Do we need to test that they are sending and receiving proper HTTP error codes?
                    * [Jeremy] Third parties are requesting data in a manner that does not create a Denial of Service (DoS) attack
                      * [Jeremy] Should the Third Party certification focus more on the utility onboarding process rather than the operation aspects?
                          * [Dee] Responded that the certification should focus on the operation and security aspects
            * [Don] Does a Third Party Application properly request OAuth 2.0 access tokens?
                * [Don] Does a Third Party properly request OAuth 2.0 access tokens request?
                * [Don] Does a Third Party properly handle Notification Endpoint requests?
                * [Don] Does a Third Party know how to tell the type of Interval received?
                * [Don -- after the meeting] Does a Third Party know how to convert UTC to local time zone?
                * [Don -- after the meeting] Does a Third Party know how to convert UTC to Daylight Savings Time?
            * [Luke] Also indicated the Certification Rules for Third Party Applications should be the highest priority of the 50% group

* The call ended without covering any of the remaining items on the agenda

## Closing Discussion
* Consensus to commit this to repo? Yes