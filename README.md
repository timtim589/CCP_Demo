# CCP_Demo
A simple repository hosting Codeless Connector Platform (CCP) samples for Microsoft Sentinel.

The use of the files in this repository will be exaplined in my blog series on medium. You
can find the first entry in the series [here](https://medium.com/@TimGroothuis/creating-a-ccp-connector-part-1-ab232a55bca9).

## Contents:
This repository contains a `data` folder, a `Data Connectors` folder and a 
`SolutionMetadata.json` file.
- The contents of the `data` folder and the `SolutionMetadata.json` file are only there
to allow packaging using the Sentinel `CreateSolutionV3` tool and can largely be ignored.
- The `Data Connectors` folder contains the actual templates of the CCP connector. 

The CCP connector consists of 4 templates:
- A `dataConnectorDefinition.json` file, which serves as the GUI.
- A `dataConnectorPoller.json` file, which serves as the definition of the API of the remote system,
the system we want to onboard.
- A `dcr.json` file, the data collection rule which will handle the data retrieved by the poller.
It supports all the features normal DCR's support, so there are multiple roads to Rome.
In this case, I went with a simple catch-all stream and some simple parsing based on unique
properties, but you could very well provide each poller with it's own, distinct stream.
- A `table.json` file, containing the 3 tables expected by the DCR.


