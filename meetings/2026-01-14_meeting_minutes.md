# OpenADE Task Force Meeting 2026-01-14

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


## NAESB ESPI Standard Proposed Changes for ESPI Version 4.1
* Remove SFTP as a transport option from the ESPI standard
  * The NAESB ESPI Task Force will meet on January 29th at 1:00 PM EST to discuss Standard Request R25005
    * If your company is a member of NAESB, please consider attending to represent the OpenADE Task Force
    * Non-members of NAESB can attend but must register in advance and pay a meeting participation fee 
  
## GBA Technical Resource Sample Code Segments
* Over the last few months we have received several requests for code segments to help implementers get started
* What code segments would be most helpful to include in the GBA Technical Resource?
  * Examples might include:
    * UUID Generation
    * BatchList handling
    * DateTime formatting
    * What else?
    * In what programming languages?
    * In what formats (e.g., code snippets, libraries, etc.)?
    * Where should these code segments be hosted (e.g., GitHub, GBA website, etc.)?

## Customer Bulk Authorization Use Case
* Is there a need for a customer to simplify account authorization for multiple accounts at once?
  * Open Discussion


## Open Discussion

## Attendees
* Donald F Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data Energy Services)
* Gary Cook (Josten)
* Valdis Hellevik (Green Button Alliance)
* Morgan Harrison (UtilityAPI)
* Ekaterina (Kat) Rubin (City of Toronto)


## Minutes

## Key takeaways
- The SFTP removal proposal has been accepted by NAESB and will be discussed at the ESPI Task Force meeting on January 29th
- The team will develop code samples and libraries to help third parties implement Green Button, focusing on TypeScript/JavaScript and Python
- A bulk authorization concept is being developed to allow customers with multiple accounts to authorize access without needing to repeating the OAuth Authorization portion for each account
- New sandbox development is underway with separate resource and authorization servers to better support third-party testing


# Discussed topics
## SFTP removal proposal status
  Donald updated the group on the status of the proposal to remove SFTP as a transport option.
- Details
  - Donald: The request to remove SFTP as a transport option has been accepted by NAESB
  - Donald: The proposal will be discussed at the ESPI Task Force meeting on January 29th
  - Donald: If it passes the ESPI Task Force, it will go to the RMQ Executive Committee meeting
  - Jeremy: The first meeting of the ESPI Task Force will be on January 29th
  - Donald: The RMQ Executive Committee meetings are held approximately every 6 months, with the last one in October
- Conclusion
  - The proposal is moving forward in the approval process
  - After passing both committees, there will be a 30 or 90-day period for public comment

  
## Code samples and libraries for third parties
  Donald and Jeremy discussed providing code samples to help third parties implement Green Button.
- Details
  - Donald: They receive frequent requests for code samples, particularly for parsing software
  - Donald: A recent request was for Python parsing software, which they found but had limitations
  - Gary: Code snippets around XML transaction handling would be helpful for new developers
  - Gary: Their implementation uses TypeScript and converts XML to JSON for processing
  - Morgan: Confirmed that TypeScript/JavaScript and Python are the most common languages used by third parties
  - Kat: Mentioned she's most familiar with Python and will be using it for her implementation
  - Donald: Suggested providing code for UUID calculation, XML marshalling/unmarshalling, and OAuth flows
- Conclusion
  - The team will work on developing code samples in multiple languages, prioritizing TypeScript/JavaScript and Python
  - They will focus on common challenges like UUID handling, XML processing, and OAuth implementation
  - The samples will be generic enough to be useful without providing complete solutions

## Bulk authorization concept
  Donald discussed a concept for allowing customers with multiple accounts to authorize access without repeating the OAuth flow for each account.
- Details
  - Donald: A utility requested a way for customers to issue bulk authorizations
  - Donald: The use case involves commercial customers with multiple facilities/accounts who want to authorize access without repeating the process for each account
  - Donald: The customer would authenticate once with the utility, select all accounts they want to authorize, and the system would handle the authorization codes sequentially
  - Gary: Expressed interest in the concept for commercial properties with multiple meters
  - Kat: Mentioned this would be useful for the City of Toronto, which has about 300 properties to manage
  - Morgan: Asked for clarification on whether this would handle both single-login multiple-account scenarios and multiple-login scenarios
- Conclusion
  - Donald will develop diagrams showing the flow and share them with Gary, Ekaterina, and Morgan
  - The concept would help commercial customers with multiple accounts streamline the authorization process
  - The implementation would require both utility and third-party support
    
## Sandbox development
  Donald shared updates on the development of a new sandbox environment.
- Details
  - Donald: The new sandbox will have separate resource and authorization servers
  - Donald: It will support the OpenID dynamic registration interface
  - Gary: Suggested including the ability to test OAuth processes including token refresh
  - Donald: The sandbox will initially only support GET operations as that's what utilities allow third parties to do
  - Donald: The authorization server will be full-featured to support OAuth flows
  - Donald: They're considering ways to generate data periodically so it looks current
- Conclusion
  - The new sandbox will better support third-party testing
  - It will include OpenAPI documentation
  - The design will focus on realistic utility API behavior

## Action items
- Donald
- [ ] Develop diagrams showing the bulk authorization flow
- [ ] Share the bulk authorization concept with Gary, Ekaterina, and Morgan before the next meeting
- [ ] Continue development of the new sandbox with separate resource and authorization servers
- [ ] Work with Jeremy on code samples for third parties in TypeScript/JavaScript and Python

 
- Jeremy
- [ ] Work with Donald on code samples for the technical page
- [X] Add Ekaterina to the email list for future meetings


- Gary
- [ ] Provide notes on challenges encountered when implementing Green Button
- [ ] Connect with Ekaterina to discuss third-party implementation

 
- Kat
- [ ] Review the email from Jeremy with membership information
- [ ] Consider options for technical support from the Green Button Alliance
