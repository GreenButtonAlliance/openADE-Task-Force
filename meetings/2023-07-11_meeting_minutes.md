# OpenADE Task Force Meeting 2023-07-11

## Agenda
* Welcome/Introductions
* Review GH repo (https://github.com/GreenButtonAlliance/openADE-Task-Force)
* Discuss GH repo layout
  * NAESB REQ.21 ESPI Standard Implementation Issues
  * GBA Certification Platform Updates
  * ESPI Standard Specification Updates
* Elect maintainers

## Attendees
* Donald F. Coffin (Green Button Alliance)
* Daniel Roesler (UtilityAPI)
* Bailey Kane (UtilityAPI)
* Brett Marraccini (UtilityAPI)
* Ben White (Arcadia)
* Michael Jensen (Arcadia)
* Dee Hastery (Big Data Energy Services)
* Steven Rajkumar (Hydro One)


## Minutes
* Don
  * Intros: Daniel, Bailey, Brett, Ben, Michael, Dee, Steven
  * Discussed the purpose of the OpenADE Task Force GH repository
  * Discussed current repository layout
  * Discussed GH repo usage
    * Track NAESB REQ.21 ESPI implementation issues
    * Track additions to the GBA CMD/DMD Certification platforms
    * Track updates to the NAESB REQ.21 ESPI standard

  * Arcadia (Ben or Michael)?
    * Asked if NAESB REQ.21 ESPI updates would be discussed during Task Force calls or elsewhere

  * Don
    * Provided the function of the OpenADE Task Force to discuss and prepare NAESB REQ.21 ESPI updates
      * The OpenADE Task Force then submits a request to NAESB for consideration
    * The NAESB request review process was then described

    * Existing GH repository issues were then reviewed
      * The current Retail Customer schema does not allow Meter Id and UsagePoint correlation [#1](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/1)
      * Add a new Function Block to the CMD and DMD Certification Platform to test Billing Line Items [#2](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/2)
      * Develop a schema API mapping approach that supports migration between NAESB ESPI standards [#3](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/3)
      * Add support for OAuth 2.0 Public Clients to the NAESB ESPI standard and incorporate [RFC 7636](https://datatracker.ietf.org/doc/html/rfc7636) [#4](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/4)
      * Add support for Billing PDF Statements to the NAESB ESPI standard [#5](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/5)
      * Add support for OAuth 2.0 JSON Web Token (JWT) Access Tokens to NAESB ESPI Standard [#6](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/6)

  * Arcadia (Ben or Michael)?
    * Suggested that the Issues affecting the NAESB ESPI standard reference the specific section of the standard 
      affected
      * Don responded that all issues are new and will reference the affected NAESB ESPI sections

*  Elect Maintainers:
  * Nominees: Donald F. Coffin
  * Elected by unanimous consent

## Closing Discussion
* Next Issues to be addressed
  * The current Retail Customer schema does not allow Meter Id and UsagePoint correlation [#1](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/1)
  * Develop a schema API mapping approach that supports migration between NAESB ESPI standards [#3](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/3)
* Consensus to commit this to repo? Yes
