# OpenADE Task Force Meeting 2024-03-13

## Agenda
* Welcome
* Review and approve minutes

* Work on highest priority requests from the GBA Survey
    * Code Snippets
        * Code Snippets currently available on the GBA website
            * powerOfTenMultiplier Usage Code Snippet
            * Namespace Implementation Code Snippet is covered in the "Atom & ESPI" webpage
                * Namespace may be defined either at the Root or Inline
        * Discuss and prioritize new code snippets from February 14th meeting
            * What is the code flow a third party developer needs to use to obtain an access token?
                * Which access token type (i.e., client_access_token, customer access_token, 
                  or registration_access_token) initial access token request or regeneration?
            * What portions of the access token response should the third party developer save?
            * How should a Utility developer revoke an access token?
            * How should a third party developer revoke an access token?
            * Retail Customer revokes consent for a specific meter data stream
            * Retail Customer revokes consent for a sub meter data stream
            * Retail Customer moves out
            * Retail Customer moves out and then in to another service location
            * Utility "swaps" meter
            * Utility "removes" meter (i.e., there is no meter at the location)

* Work on OpenADE Task Force issues:

    * Issue #1 -- Correlation of Multiple UsagePoints for a ServiceLocation - [#1](https://github.
      com/GreenButtonAlliance/openADE-Task-Force/issues/1)
    * Render - https://www.greenbuttonalliance.org/issue-001
        * NAESB Corrective Request submitted to NAESB

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data Energy Services)
* Jeremy J. Roberts (Green Button Alliance)
* Daniel Roesler (UtilityAPI)
* Heather Hendy (ACTuate Facility Tech)
* Valdis Hellevik (Green Button Alliance)
* Klaar De Schepper (Flux Tailor)

## Minutes
* Welcome and introductions
* Review minutes from the February 14th meeting
    * Consensus to approve minutes? Yes 
* Review and prioritize new code snippets from the February 14th meeting
    * Reviewed code snippets currently available on the GBA website
        * powerOfTenMultiplier Usage Code Snippet
        * Namespace Implementation Code Snippet
            * [Don] Asked for suggestions on how to make the Namespace Implementation style consistent
            * [Daniel] Indicated most HTML parsers can handle either style
            * [Jeremy] Responded that not all HTML parsers are able to handle the importation of the Atom schema
            * [Don] Commented that the current posted NAESB REQ.21 ESPI version 4.0 schema files cannot be parsed by 
              the DMD Validator or the CMD Certification Platform due to a typo in several elements of the file
            * [Daniel] Suggested that the file is probably correct and turning off the schema validation would allow 
              the file to be parsed
            * [Dee] Indicated she is having schema validation issues from a non-certified utility
            * [Don] Commented that a Root based Namespace is also included in the field tag value but not when the 
              Namespace is Inline, so the CMD Certification Platform has to test for both tag formats
            * [Don] Asked if the GBA Code snippets should use Inline Namespace format only?
                * [Jeremy] Indicated the Atom Link code snippet uses the Root Namespace to be sure readers could 
                  tell the difference between atom, espi, and cust Namespaces and to simplify the code snippet
                * [Dee] Agreed that using the Root Namespace in the code snippet is okay
                * [Klaar] Asked if the addition of new Namespaces would make the Inline Namespace format more practical
                * [Don] Responded to Klaar that Dee had recommended using the Root Namespace format in the code 
                  snippet and that all existing code samples use the Root Namespace format
                * [Klaar] Agreed that using one format rather than both would be better and that the Root Namespce 
                  format is more practical though had heard complaints about the verbosity of the Root Namespace format
                * [Don] Indicated that all code snippets would use the Root Namespace format
    * Discussed the prioritization of new code snippets from the February 14th meeting
        * What is the code flow a third party developer needs to use to obtain an access token?
            * Initial access token request or regeneration?
                * [Don] Asked which access token type (i.e., client_access_token, customer access_token, 
                  refresh_token or registration_access_token) flow do third party developers need documented?
                * [Don] Indicated the customer_access_token is the access token used the most by third party 
                  developers followed by the client_access_token requests and that the registration_access_token 
                  should rarely be used
                * [Don] Stated that the priority should logically be for the customer_access_token flow followed by 
                  the client_access_token flow
                * [Don] Developing code snippets for the OAuth 2.0 access token flows is a bit challenging and are 
                  likely best handled by webpage write-ups similar to the powerOfTenMultiplier Usage Code Snippet 
                  with segments of code
                * [Heather] Indicated she doesn't have much experience in the OAuth 2.0 access token flows yet, but 
                  that code snippets in other areas would definitely help her out.
                * [Don] Replied to Heather that the GBA offers technical training and that the OAuth 2.0 standard is 
                  available and has data samples and that UtilityAPI's website also has documentation on their website
        * What portions of the access token response should the third party developer save?
            * [Don] Indicated that a code snippet showing what portions of the access token response should be saved 
              by a third party developer is relatively straight forward and can be handled with a code snippet
        * Itron submitted code snippet requests for the following:
            * [Don] Indicated that a couple of the Itron requests are code snippets but others are Use Cases are
              how should a utility implement the indicated Use Case
                * [Don] Indicated that the configuration of a utility's Authorization and Resource Server play a
                  major part in how some of the Use Cases (i.e., revoking access tokens) are implemented
            * How should a Utility developer revoke an access token?
                * [Don] An access token should be revoked by using the Authorization Servers /revoke endpoint
            * How should a third party developer revoke an access token?
                * [Don] An access token should be revoked by using the Authorization Servers /revoke endpoint
            * Retail Customer revokes consent for a specific meter data stream
                * [Don] Stated the customer must revoke a specific meter using the utility's customer portal
                * [Daniel] Revocation of a meter impacts the scope of the current access token which means the 
                  customer must revoke the current access token and request a new one
                * [Don] Confirmed Daniel's process is the method used to increase the scope of a current access 
                  token and is likely how decreasing the scope of a current access token should be handled
                * [Daniel] Asked if the token introspection (i.e., /token_info) endpoint could be used to determine 
                  the scope of the current access token has changed?
                * [Don] Responded that the current NAESB REQ.21 ESPI standard scope format does not indicate which 
                  meters are included in the scope of the access token, so the token introspection endpoint would 
                  not be able to tell a third party developer if a specific meter has been revoked
                * [Daniel] Agreed that a an access token scope cannot be currently modified, nor can a specific meter 
                  be revoked from the access token scope
            * Retail Customer revokes consent for a sub meter data stream
                * [Don] Indicated the discussion for revoking a meter applies to sub meters as well
            * Retail Customer moves out
                * [Don] Indicated that the existing access token is revoked when the customer moves out and they are 
                  no longer able to access their old recidence's data
            * Retail Customer moves out and then in to another service location
                * [Don] Indicated that the customer must initiate a new access token request for the new service 
                  location with the third party developer and is only able to access data from their new service 
                  location
                * [Daniel] Discussed the UtilityAPI's "meters all" authorization option that allows a customer 
                  to authorize access to current and all future meters added to the customer's account
                * [Don] Responded that the option is for campus like settings where the customer has multiple meters 
                  at the same service location and that the Itron Use Case is for a customer moving to a new service 
                  location
                * [Daniel] Agreed that the UtilityAPI "meters all" option is for campus like settings and not 
                  residential service locations
                * [Don] Indicated modifying the OAuth access token scope to include specific meters as part of the 
                  access token scope is a possible future enhancement to the NAESB REQ.21 ESPI standard
                * [Daniel] Then described a methodology for how a third party developer could use the Retail 
                  Customer Service Location ID to determine the meters at the service location
                * [Don] Confirmed that Daniel's methodology is a valid method for determining the meters at a service 
                  location but the current NAESB REQ.21 ESPI ver 3.3 and 4.0 Customer Retail schema does not allow a 
                  third party developer to determine the UsagePoint's meter ID
                * [Don] Commented that he is working on a change to the NAESB REQ.21 ESPI standard to allow a third 
                  party developer to determine the UsagePoint's meter ID
                * [Daniel] Commented that to make his methodology work, the customer would have to provide the 
                  third party developer access at the Service Location level rather than at the individual meter level
                * [Daniel] Added that large property management companies have hundreds of properties on their 
                  energy portfolio and only want to authorize access at the service location level and not the meter 
                  level
                * [Don] Asked Daniel if he could provide a document on how to implement his methodology
                * [Jeremy] Stated he'd like to be able to classify how the use cases would work, for example, the 
                  customer only wants authorization for electricity, not natural gas, or possible only for Electric 
                  Vehicles
                * [Daniel] Indicated the customer must still review and approve the various checkboxes as part of 
                  their authorization process
                * [Jeremy] Asked if it would be possible to have multiple scope versions for the access token
                * [Daniel] Agreed there could be multiple scope versions representing the various checkboxes the 
                  customer could approve
                * [Don] Acknowledged that the schema historically have been developed with a focus on residential 
                  customers and that the schema development approach needs to be broadened to take into 
                  consideration commercial property management companies and industrial/educational campuses
            * Utility "swaps" meter
            * Utility "removes" meter (i.e., there is no meter at the location)

## Closing Discussion
* [Don] Requested that any ideas or suggestions for discussion during the next meeting be emailed to him
* Consensus to commit this to repo? Yes
