# OpenADE Task Force Meeting 2026-03-11

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


## NAESB ESPI Standard Changes for ESPI Version 4.1
* SFTP has been removed as a transport option from the ESPI standard
  * The NAESB RMQ Executive Committee met March 4th and approved removal of the SFTP as a transport protocol from 
    the NAESB ESPI standard.
* NAESB Minor Corrections
  * Minor correction MC25009 to correct the ESPI Version 4.0 standard's inconsistency with how DEPRECATED elements 
    are shown was approved by a simple majority of the NAESB RMQ Executive Committee on March 4th.
  * Minor correction MC26001 to correct ESPI Version 4.0 standard's Figure 2.0 to indicate the TimeConfiguration 
    resource also inherits from IdentifiedObject
  * The requests (R25009 & R26001) are currently undergoing a 14-day [review and comment]
  * (https://www.naesb.org/retail_minor_corrections.asp) period until March 18th, 2026.

## Additional NAESB ESPI Standard Changes
* The next meeting of the NAESB RMQ Executive Committee will be held on October 22nd, 2026.
* The following will be submitted to NAESB over the summer.
  * Simplify the ESPI Customer schema to reflect the same organization for Customer and IdentifiedObject as exist in 
    the espi.xsd schema.
  * Refactor the ESPI standard to reflect elements that are actively supported by utilities.
    * Remove POST, PUT, and DELETE operations for Resource Servers from the ESPI standard.
      * Affects Section REQ.21.6.2.1 ESPI REST API Interface

## Impact on CMD Certification
* Changes to the CMD Certification Platform due to SFTP Protocol removal
  * All SFTP Function Blocks will be removed from the CMD Certification Platform
    * [FB_34] SFTP for Bulk (Energy Usage)
    * [FB_66] SFTP for Bulk (Retail Customer)

## Open Discussion
* URPX Utility Rate Plan Exchange Standard Update

## Attendees
* Donald F Coffin (Green Button Alliance) (Maintainer)
* Jeremy J Roberts (Green Button Alliance)
* Valdis Hellevik (Green Button Alliance)
* Klaar de Schepper (Flux Tailor)


## Minutes

## Key takeaways
- NAESB approval received to delete SFTP protocol transmission from Green Button standard version 4.1, currently in 14-day public review until March 18th
- Two minor corrections approved for version 4.1: consistency in deprecated elements display and diagram updates for resource inheritance
- Proposal submitted to simplify retail customer schema by removing unnecessary pass-through classes
- Recommendation to remove POST, PUT, and DELETE operations from Green Button REST API, retaining only GET operations
- Klaar presented URPX (Utility Rate Plan Exchange Standard), now an LF Energy standard, aiming for ISO certification
- URPX seeks integration with Green Button for customer data and bill line items mapping

## NAESB ESPI Standard Changes for ESPI Version 4.1
### Details
  - Donald: Request approved by RMQ Executive Committee last week, in 14-day public review until March 18th, publication expected in April as part of Green Button version 4.1
  - Donald: Had 15-minute discussion in task force with someone using SFTP for EDI who misinterpreted the scope as removing SFTP across all standards
  - Jeremy J Roberts: Removal is timely as sandbox is being rebuilt from scratch, and implementing SFTP when nobody uses it is unnecessary extra work
  - Jeremy J Roberts: SFTP was never properly implemented by most parties, with security issues around shell access and dual authorization systems
  - Klaar: Removal makes sense for Green Button's argument against master key approach used in EDI
  - Donald: SFTP was included originally because one California IOU insisted on it, but it's designed for bulk monthly operations rather than interactive daily data requests

### Conclusion
  - SFTP protocol removal approved and moving forward in version 4.1
  - Two function blocks (FB34 and FB66) will be deleted from CMD platform as result
    Minor Corrections for Green Button Version 4.1
 

## Minor corrections approved for inclusion in the upcoming ESPI standard release.

### Details
  - Donald: Minor correction 25009 addresses inconsistencies in how deprecated elements are displayed, with some showing strikethrough and others not
  - Donald: Correction also standardizes the representation of deprecated items, which had 2-3 different versions depending on editor and timing
  - Donald: Minor correction 26001 updates Figure 2 diagram to properly show resource inheritance from identified object, adding one block to right-hand column
  - Donald: All Green Button resources must inherit from identified object, requiring atom ID, rel links, published and updated tags as wrappers

### Conclusion
  - Both corrections approved and will be included in version 4.1 publication
    Retail Customer Schema Simplification

## A new request has been submitted to simplify the retail customer schema structure.

### Details
  - Donald: Request assigned as R26003, will be included in version 4.2 due to insufficient time for version 4.1
  - Donald: Simplification has no impact on output or data format, only affects programmatic representation in Java or Python applications
  - Donald: Original implementation by Marty lifted CIM model directly, creating unnecessary pass-through classes
  - Donald: Organizational role class provides no functionality, just passes through to customer and service supplier
  - Donald: Removing useless classes that were in CIM model for additional clarification and customization around documents and customer agreements

### Conclusion
  - NAESB accepted the Request (R26003) for version 4.2
  - Changes are cleanup and simplification only, no functional impact

## Proposal to remove all CRUD operations except GET from the Green Button REST API interface.

### Details
  - Donald: Proposes removing everything except GET from section REQ 21.6.2.1 Green Button REST API interfaces
  - Donald: Original rationale was utilities would post meter readings directly, but this has never happened in practice
  - Donald: Utility business structure uses back-end meter collection systems that translate raw data to database, then retrieve as Green Button format using only GETs
  - Donald: No utility has been certified for POST, PUT, or DELETE in 150+ certifications over the years
  - Donald: In today's security environment, allowing POST and PUT with string data could create significant security vulnerabilities
  - Klaar: Questioned reasoning, suggested it could be about reducing vendor risk and increasing adoption likelihood
  - Klaar: Proposed creating to-do task for future DER use cases and interoperability scenarios where PUT might be needed
  - Klaar: Suggested presenting removal with link to future investigation issue to address concerns
  - Donald: Acknowledged DER-oriented POST operation could be submitted as SEP but doubts it would pass NAESB Task Force
  - Donald: Referenced ongoing 2-year cybersecurity committee discussions about CVE notification requirements and liability transfer to vendors

### Conclusion
  - Proposal to remove POST, PUT, DELETE operations moving forward
  - Possibility left open for future DER-specific API development
  - DELETE makes clear sense as no one would allow external parties to delete records

## URPX Utility Rate Plan Exchange Standard Update

### Details
  - Klaar: Presented comprehensive update on URPX standard development and goals for Green Button integration.
  - Klaar: Work began August 1st, approved by LF Energy on November 19th as Standards and Specifications standard
  - Klaar: Goal is ISO certification as international standard, will be W3C standard
  - Klaar: Covers rate plans, rate plan modifiers, structured eligibility rules, detailed pricing, time of use schedules, and traceability to official tariff documents
  - Klaar: Packages data currently scattered across tariff books, downloadable CSVs, addendums, and adjustment documents
  - Klaar: Provides single data stream for rate plan and customer situation to plug into cost modeling
  - Klaar: Based on OWL ontology with data instances in JSON-LD, following semantic web standards
  - Klaar: Will have documentation site and sandbox in future
  - Klaar: Seeking integration with Green Button pricing structure URI in customer schema
  - Klaar: Wants to map detailed price definitions to line items on bills for bridge between systems
  - Klaar: Vision is customers with Green Button integration can import parameters for customer profile to pull correct rate plan prices
  - Klaar: Bruce Nordman is OpenADR focus expert, Don Jackson connected to MATTER standard efforts
  - Klaar: Team includes Danny Schmidt from National Laboratory of the Rockies
  - Klaar: Currently in pre-draft mode, ontology not publicly accessible pending LF Energy IP review
  - Klaar: Materials under Apache 2.0 license, officially handed over from FluxTailor to LF Energy
  - Klaar: Meetings every 2 weeks to push forward more quickly
  - Klaar: Mapping to Green Button left out of current draft to avoid IP conflicts
  - Jeremy J. Roberts: Recalled previous utility bill representation phase two efforts and ideas for machine-readable line items
  - Donald: Welcomed update and collaboration opportunity

### Conclusion
  - URPX moving forward as LF Energy standard with goal of ISO certification
  - Integration with Green Button planned for customer data and bill line items
  - Klaar will request access for Donald and Jeremy to pre-draft materials
  - Pilot project planned to demonstrate integration

## Action items
### Klaar
  - Request LF Energy permission to give Donald and Jeremy access to ERPEX pre-draft repository with draft mappings
  - Follow up on Green Button integration points for ERPEX, specifically pricing structure URI and bill line items mapping
  - Coordinate pilot project to demonstrate ERPEX and Green Button integration
### Donald
  - Update meeting minutes with correct request number for retail customer schema simplification (R26003 or similar)
  - Monitor public review period for SFTP removal through March 18th
  - Consider submitting NAESB Request for DER-oriented POST operation with acknowledgment of future investigation
### Jeremy J Roberts
  - Review previous Slack discussions about utility bill representation phase two and machine-readable line items structure
  - Continue sandbox rebuild without SFTP support
### Task Force
  - Await Green Button version 4.1 publication, expected in April
  - Prepare for version 4.2 development cycle with retail customer schema simplification

