---
uid: Connector_help_Eutelsat_Path_Detection_Service_Protocol
---

# Eutelsat Path Detection Service Protocol

With this advanced service protocol, you can efficiently monitor the signal path of a service.

The connector leverages the basic service protocol used to create enhanced services and augments it with path detection logic.

> [!NOTE]
> This service protocol requires DataMiner version **9.0.3.0** or higher.

## About

### Version Info

| Range              | Key Features     | Based on    | System Impact    |
|--------------------|------------------|-------------|------------------|
| 1.0.0.x [SLC Main] | Initial version  | -           | -                |

### Product Info

| Range     | Supported Firmware     |
|-----------|------------------------|
| 1.0.0.x   | -                      |

### System Info

| Range     | DCF Integration     | Cassandra Compliant     | Linked Components    | Exported Components    |
|-----------|---------------------|-------------------------|----------------------|------------------------|
| 1.0.0.x   | No                  | Yes (1.0.0.6+)          | -                    | -                      |

## Configuration

### Creation

This protocol is intended to be used for services. When you create a service, in the advanced options section, select it as the service protocol. Then select the necessary elements and parameters, as described under [Adding a service](https://aka.dataminer.services/adding-a-service).

### Initialization

Go to the **General** page and specify the CGL TNM-7222-D Amethyst III and CISCO DCM elements that need to be monitored.

You can right-click the **DCM I/O Configuration** table to input information via the context menu.

## Usage

Once you have correctly configured the elements that need to be monitored (see "Initialization"), the **DCM Active Input** table will closely monitor the active DCM input and the Amethyst active input. It will also calculate and display the currently active path, which could be TH1, TH2, or a Warning state.
