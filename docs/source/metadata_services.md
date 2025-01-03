# Metadata Services 

This page briefly outlines the options for writing metadata and the services provided by AIND scientific computing for generating some metadata files. 

You can write metadata yourself using the [aind-data-schema](https://github.com/AllenNeuralDynamics/aind-data-schema) library (requires python) or use the [AIND metadata entry app](https://metadata-entry.allenneuraldynamics.org/) (no coding).  

Some metadata files are automatically generated through the [aind data transfer service](http://aind-data-transfer-service/) when data is uploaded to the cloud. The data transfer service relies on the [aind metadata service](http://aind-metadata-service/) to retrieve information from AIND internal databases for the subject and procedure files. 

| Metadata File       | Description                                                                                                   | aind-data-schema | metadata entry | aind-data-transfer-service |
|----------------------|---------------------------------------------------------------------------------------------------------------|------------------|----------------|---------------|
| Data description     | Administrative information about a data asset      | [x]              | [x]            | [x]           |
| Subject              | Information about animal subject    | [x]              | [x]            | [x]           |
| Procedures           | Procedures performed on a live subject or procedures performed on extracted tissue                  | [x]              | [x]            | [x]*          |
| Rig/Instrument       | Hardware/software used for a data asset. `rig.json` for physiology and behavior data, `instrument.json` for light sheet or confocal imaging | [x]              | [x]            |               |
| Session/Acquisition  | Hardware/software information specific to the data collection. `session.json` for physiology and behavior data, `acquisition.json` for light sheet imaging | [x]              | [x]            |               |
| Processing           | Information about data processing steps applied to the data asset                                            | [x]              | [x]            | [x]**         |
| Quality Control      | Assessment of the quality of raw, processed, and analyzed data assets                                        | [x]              | [x]            |               |

*captures most surgeries, injections and perfusions performed by the Neurosurgery and Behavior and Lab Animal Services teams at AIND 

**the data transfer service creates a processing.json file with information about data compression or other pre processing applied prior to data upload. an additional processing.json file should be created for derived data assets, where further processing steps were applied to the original data asset. 
