# OpenADE Task Force Meeting 2025-08-13

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


## Technical Topic
* Review current Technical Activities
  * CMD Certification Platform Pending Updates
    * [FB_58] Retail Customer ServiceLocation Information Update (currently being updated)
      * Verify ServiceLocation Resource UsagePoint entries contain valid URLs that match the associated UsagePoint 
        atom <link> href attribute
  * GBA Sandbox
    * The GBA Sandbox is currently being updated to support the latest ESPI standard
      * Will support ESPI version 4.0
        * TLS support will be limited to TLS 1.3
      * Will only support GET REST API calls
      * Will provide an OpenAPI compliant website replacing the current Green Button API Documentation website

## ESPI Support for Steam Data
* Work on how to report Steam data using Green Button is under way
    * Steam data can be reported using the ESPI UsagePoint resource
        * The UsagePoint can be associated with a MeterReading and ReadingType resources
        * The ReadingType resource can specify the type of data being reported
        * The UsagePoint can also include a ServiceLocation to specify where the steam is being used
    * Currently working on how to measure the amount of steam used
        * Steam usage can be measured in various ways, such as:
            * Volume (e.g., cubic feet or cubic meters)
            * Mass (e.g., pounds or kilograms)
            * Energy content (e.g., BTUs or Joules)
        * The choice of measurement method will depend on the specific application and the available data
    * Once the measurement method is determined, examples of how to report steam using the ESPI standard will be created
        * These examples will be posted as a technical article on the GBA website
        * Samples of ESPI XML data covering all steam use cases will be provided
    * The goal is to have the technical article and examples completed by the end of September

## Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data Energy Services)
* Mike Foye (Paymentus)
* Valdis Hellevik (Green Button Alliance)
* Morgan Harrison (UtilityAPI)


## Minutes
[Don]: Asked permission to record the meeting, opened the meeting and welcomed the attendees.
[Attendees] Introductions made by Don, Valdis, Dee, Mike, and Morgan.
[Valdis]: Yeah, we can see it, Don.
[Don]: Reviewed the minutes from the July 9, 2025, OpenADE Task Force meeting. Asked for any changes or corrections. Several changes were noted, the minutes were approved with corrections.
[Don]: Discussed the agenda topics.
## Function Block 58 (Customer Service Location) Updates
- **Current Issues**:
    - Service location UsagePoint entries contain invalid URLs (some relative, some not URLs at all)
    - CMD certification platform now validates these URLs are valid
    - DMD validator has been updated for data element testing

- **Upcoming Changes**:
    - Function Block [58] will verify URLs match UsagePoint atom <link> rel="self" href= attributes in the related 
      energy usage data
    - Will also identify duplicate UsagePoint entries and invalid UsagePoint collections
    - Implementation is expected by the end of September
    - The project was on hold due to active certifications with deadlines

## GBA Sandbox Update
- **Current Status**:
    - API documentation webpage not working
    - The current sandbox is 13 years old and unable to build/execute

- **Planned Updates**:
    - Upgrading to version 4.0 of the standard (from 3.3)
    - Will support PDF statements
    - Only supporting TLS 1.3
    - Updating to the latest Spring Boot
    - Will include three parts: resource server, client server, and authorization server
    - Will support OpenID Connect

- **Benefits**:
    - Run as an independent sandbox for third-party testing
    - Fix database reset issues
    - Resolve connection timeout problems

- **Timeline**: Targeting fourth quarter completion

## Green Button Support for Steam Data
- **Background**:
    - A utility has requested Green Button support for steam data (used for heating homes)
    - UsagePoint already has meter reading and reading type resources

- **Implementation Approach**:
    - ReadingType will indicate steam flow (standard already includes steam)
    - Three measurement options for steam: volume, mass, and energy
    - Current issue: "pounds" unit is requested but not in the current enumeration

- **Options Being Considered**:
    - Get a correction without changing the current NAESB standard version
    - Add to enumeration (requires NAESB version 4.1)
    - Alternative: convert pounds to kilograms in implementation

- **Deliverables**:
    - Technical document with use cases and conversion methods
    - To be posted on GBA website
    - Expected completion by the end of September/October

## TLS Compatibility Concerns
- Version 4.0 requires TLS 1.3 for all communications
- Problem: Many gateway implementations need to support multiple TLS versions (1.1, 1.2, 1.3)
- Considering allowing version 3.3 implementations to use PDF statement capability
- This would avoid forcing upgrades to TLS 1.3 exclusively
- Discussion is ongoing about certification standards and versioning

[Morgan]: Expressed support for the proposed approach regarding PDF capabilities and versioning, while highlighting 
concerns about implementation challenges:
1. **Agreement with Direction**: Morgan approves of the task force's approach to potentially allowing version 3.3 implementations to use the new PDF statement capability.
2. **Implementation Challenges**:
    - UtilityAPI's current systems are all on ESPI version 3.3
    - They want to utilize the new PDF statement capability available in version 4.0
    - The most significant technical challenge ("biggest lift") for their team would be upgrading to TLS 1.3, which is required in version 4.0

3. **Overall Sentiment**: Positive about the direction of the discussion, indicating the proposed flexibility would be helpful for their implementation needs.

[Don]: Thanked Morgan for the feedback and addressed issues related to CMD certification versioning and TLS compatibility.

## Versioning and Certification Issues
1. **Board Prioritization Challenge**:
    - There's difficulty getting the ESPI versioning topic in front of the board due to other higher-priority matters
    - Hope to resolve this issue before year-end 2025
    - Implementation is described as "not going to be that hard"

2. **Certification Documentation Gap**:
    - Current certification documents don't clearly indicate whether testing is for version 3.3 or 4.0
    - This creates confusion for implementers

3. **Standard Purchasing Process**:
    - When purchasing the standard, customers automatically receive version 4.0
    - To get version 3.3, customers must specifically request it and have their registration updated
    - This is described as a "technical paperwork thing"

## Technical Compatibility Challenges
1. **TLS 1.3 Requirement Obstacle**:
    - Version 4.0's TLS 1.3 requirement creates significant upgrade difficulties
    - Many organizations use domain gateways serving multiple backend systems
    - These organizations can't reasonably upgrade all backend systems to TLS 1.3

2. **Certification Testing Approach**:
    - Current policy is to test for the version requested (3.3 or 4.0)
    - Need to develop a way to differentiate between implementations needing:
        - Version 4.0 with TLS 1.3 only
        - Version 3.3 with other TLS versions

3. **CMD Certification Test Numbering**:
    - There's a need to establish a clear system for numbering CMD certification tests
    - So far, no requests for statement testing have been received, but they're expected

[Don]: Reminded Morgan that as a sponsor, UtilityAPI has access to 10 hours of technical 
support, which can be used for one-on-one technical meetings.
[Don] Reminded attendees of the next meeting on September 10, 2025, and closed the meeting.

