# OpenADE Task Force Meeting 2025-11-12

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


## NAESB ESPI Standard Proposed Changes for ESPI Version 4.1
* Remove SFTP as a transport option from the ESPI standard
  * SFTP is no longer widely used for data exchange
  * SFTP is natively not as secure as other transport options (e.g., HTTPS)
  * Discussion whether to remove SFTP from the ESPI standard entirely
* Add Steam as an Energy Type in ESPI
  * Steam is increasingly being used in industrial applications
  * Discussion on how to represent Steam data in ESPI
    * Need to define the unit of measure for Steam (e.g., lb/hr, kg/s)
    * Need to define the data structure for Steam readings
* Add Renewable Energy Certificates (RECs) as a Data Type in ESPI
  * RECs are important for tracking renewable energy generation and consumption
  * Discussion on how to represent RECs in ESPI
    * Need to define the data structure for RECs
    * Need to define the unit of measure for RECs (e.g., MWh)

    
## CMD Certification Platform Updates
* Change how CMD Certification Platform versions are named
  * The current versioning system was based on which version of the ESPI standard was supported
    * Certification Applicants are able to select which version of the ESPI standard to certify 
          against (3.3 or 4.0)
    * The current CMD Certification Platform supports both ESPI Version 3.3 and Version 4.0
    * Does not allow for version updating for new changes not related to ESPI versions
  * Proposed new versioning system
    * Major.Minor.Patch
      * Major version changes when there are significant changes to the platform
      * Minor version changes when new features or data types are added
      * Patch version changes for bug fixes and minor updates
        * Example: Version 2.1.0
        * What should the initially renamed version be?
* Release a new version of the CMD Certification Platform
  * Features to be included in the new version (assumes NAESB ESPI Version 4.1 changes are approved)
    * Support for Steam as an Energy Type
    * Support for RECs as a Data Type
    * Remove SFTP as a transport option (independent of NAESB ESPI standard changes)
* Should existing SFTP certification Function Blocks be removed or deprecated?
  * If SFTP is removed as a transport option, should SFTP certification Function Blocks be removed for Version 3.3 
    and Version 4.0?
  * Discussion on the impact of deprecating SFTP certification Function Blocks on existing certified applications


## Open Discussion

## Attendees
* Donald F Coffin (Green Button Alliance) (Maintainer)
* Dee Hastey (Big Data Energy Services)
* Daniel Roesler (Daniel Roesler LLC)
* Mike Foye (Paymentus)
* Chris Rollins (UtilityAPI)
* Gary Cook (Josten)
* Morgan Harrison (UtilityAPI)
* Jeremy J Roberts (Green Button Alliance)
* Valdis Hellevik (Green Button Alliance)



## Minutes

