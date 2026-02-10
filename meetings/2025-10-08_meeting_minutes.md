# OpenADE Task Force Meeting 2025-10-08

## Agenda
* Welcome
* Introduction of attendees
* Review and approve minutes


## Technical Topic
* Are there any issues with a hybrid Certification allowing parts of ESPI v4.0 under an implementation of ESPI v3.3?

## ESPI Support for Steam Data
* Continuing to work on how to report Steam data using Green Button
    * Currently working on how to measure the amount of Steam used
        * The current request uses lb/hr as the unit of measure
          * Not currently supported in ESPI (UnitSymbolKind enumeration)
          * What other measurement units can be used for Steam not currently supported in ESPI?
          * Only open issue needing resolution before developing ESPI XML data examples

## ESPI Support for Carbon Emissions Data
* GBA wants to investigate adding support for Carbon Emissions data in ESPI
    * This would be an optional element to ESPI
    * Discussion on how to represent this data
        * Could be a new resource or an extension of existing resources (IntervalReading)
        * Need to consider how to represent different types of emissions (e.g., CO2, CH4)
    * Need to speak with utilities to understand their requirements and capabilities

## ESPI Support for Renewable Energy Certificates (RECs)
* GBA also wants to investigate adding support for RECs in ESPI
    * Discussion on how to represent RECs in ESPI

## Open Discussion

## Attendees
* Donald F. Coffin (Green Button Alliance) (Maintainer)
* Jeremy J. Roberts (Green Button Alliance)
* Valdis Hellevik (Green Button Alliance)
* Dee Hastey (Big Data Energy Services)
* Mike Foye (Paymentus)
* Gary Cook (Jotson)
* Klaar de Schepper (Flux Tailer)
* Daniel Roesler (Daniel Roesler LLC)

## Minutes

