# OpenADE Task Force Meeting 2023-11-07

## Agenda
* Welcome
* Review and approve minutes
* Ontario, Canada provincial Green Button rollout
    * Implementation issue tracking system
* Work on OpenADE Task Force issues:
    * Issue #5 Update - [#5](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/5)
    * Render - https://www.greenbuttonalliance.org/issue-005
    * Issue #1 - [#1](https://github.com/GreenButtonAlliance/openADE-Task-Force/issues/1)
    * Render - https://www.greenbuttonalliance.org/issue-001
* New York ISO (NYISO) ITAG and PJM PLC wholesale market data requirements

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Klaar De Schepper (Flux Tailor)
* Dee Hastey (Big Data ES)
* Michael Murray (Mission:data)
* Ernst Eder (GBA)
* Dan Gowans (The City of Sault Ste. Marie)
* Bob Champagne (Smart Energy Water)
* Lucas Scheidler (Itron)
* NAESB (unidentified participant)

## Minutes
* Don welcomed everyone to the OpenADE Task Force call
* Don reviewed who was on the call and then asked each participant to introduce themselves and tell how they intend
  to use the Green Button standard
  * Dan Gowans introduced himself and described how the City of Sault St. Marie plans to use the Green Button data
    to meet the cities various reporting requirements
  * Don then reviewed for Dan how he can use the OpenADE Task Force repository and discussed the possibility of
    launching a GBA Discord board
  * Dee Hastey introduced herself and discussed activity Big Data ES is working with London Hydro and ERTH Power
  * Bob Champagne introduced himself and discussed how Smart Energy Water has been involved with GBA to integrate
    Green Button support to the SEW Customer Experience platform
  * Klaar De Schepper introduced herself and discussed Flux Tailor's participation in adding the Statement
    resource to the Green Button standard and her ongoing work with the New York Green Button platform
  * Lucas Scheidler introduced himself and described his background and interest in sharing data
  * Michael Murray (Mission:data) introduced himself and the role of Mission:data
  * NAESB dropped from the meeting as they were being called upon to speak

## Canadian Standard Technical Enhancements
Don and Jeremy discussed the ongoing developments in Canada related to a provincial wide group's efforts to address 
technical issues and enhancements related to implementation of the Green Button standard. Don suggested the use of the
OpenADE Task Force to allow utilities in Ontario to raise questions and make requests for changes to the standard as 
they roll out. 

They also discussed the addition of the Statement resource to the Customer Retail schema, which is currently under 
review. Don, a member of the Retail Market Quadrant Executive Committee, announced that a document related to these 
developments was open for review and that anyone could access it, not just NAESB members.  Don expressed his hope there 
would be no comments by the end of the NAESB review period to avoid any delays. He mentioned a mistake that
needed correction and planned to submit it after the document gets published. 

Don highlighted that the Statement
resource won't be available in Canada as it will be published as version 4.0.  

## API Linkage for PDF Billing Information
Don discussed the utility of providing an API linkage for third-party access to customer billing information in PDF 
format, which has been simplified through the use of libraries to digitally process the data. Jeremy raised a question
about the schema update, emphasizing its intent to eliminate web scraping of PDFs and open up the possibility for other
digital representations. The group agreed that while the current update includes the addition of statement as a part of
the Green Button standard, more work needs to be done to fully structure the billing data in future phases.

## Meter ID Proposal for Accurate Usage Tracking
Don discussed the relationship between a specific meter ID or serial number and a usage point. He highlighted that 
the current design associates meters with a single service location, which has led to challenges in correlating 
individual meters back to the service location, particularly in cases where there are multiple meters. To address this,
Don proposed moving the meter ID or serial number to the meter itself, rather than keeping it tied to the service 
location. This change would allow for more accurate tracking and certification of usage points. However, he 
acknowledged that this proposal would need to be examined further, particularly in terms of its potential impact on 
certification processes.

Don discussed the need to address and correct specifications in Ontario according to its legislation, which mandates
the use of version 3.3. He also clarified that while minor corrections can be made, they are not complete updates of 
the NAESB REQ.21 ESPI standard.

## ITAG and PLC Support
Don further discussed the topic of how the standard supports the ITAG or the PLC and the Wholesale market, and 
anticipated that additional fields may need to be added to the usage point to accommodate the wholesale market. 
Michael mentioned another necessary consideration, the service voltage, which Don confirmed should already be 
included. The need for a new discussion on how to handle the Wholesale market was also raised.

## Structuring ITAG Support for Future Additions and Compatibility
Klaar and Don discussed the structuring of the ITAG support to allow for future additions of regional tags and 
customer program enrollment. They agreed to make new customer tags easier to add and considered using strings instead
of enumerated values for regional names. Klaar emphasized the importance of providing clear definitions for each tag 
for data interpreters. Don suggested opening an issue to discuss the technicalities of this proposal and encouraged 
any additional ideas for future-proof implementation. The team also discussed the decision to keep certain deprecated 
fields in the schema for backward compatibility with users, but due to potential issues, particularly in Ontario, they 
do not plan to remove these items.

## Review of open GitHub Issues
The priority of tasks was clarified by Don, stating that it is not determined by their number in the list, but by 
their importance.

## Certification Program Updates
Don discussed the implementation of a request to support public OAuth 2.0 clients, stating that it may have more 
of an impact on the certification platform than on the NAESB REQ.21 ESPI standard. He mentioned that the current 
proposal is for both confidential and public clients to use a specific authorization code with PKCE. Don also 
discussed the need to add new function blocks to the certification program and emphasized that most of the standard is 
optional, unless it's critical for the system to function. 

He also expressed the group's intention to avoid creating customized extensions to maintain interoperability.

## Meeting Summary: Review, Discussion, and Future Plans
Don led the discussion and wrapped up the agenda. Klaar showed interest in reviewing the previous meetings' minutes. 
Don also planned to post a detailed record of the discussion on the topic. The next meeting was scheduled for late 
November, with the possibility of addressing issues related to ITAG and PLC. Jeremy confirmed that the version 4.0 of 
the ESPI standard would be released on the 13th of December. Don emphasized the availability of assistance in using 
the system for submitting issues and encouraged everyone to participate in future meetings.

## Closing Discussion
* Consensus to commit this to repo? Yes/No