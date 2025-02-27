---
uid: Connector_help_Telefonica_UDO_Ticketing_System
---

# Telefonica UDO Ticketing System

UDO is a ticketing platform that is used to report issues from different kinds of technologies. The Telefonica UDO Ticketing System connector can create and close tickets on the UDO platform based on the alarms generated in DataMiner by Ineoquest iVMS and Ineoquest iVMS ASM elements. These alarms are related to the video channels, which are also represented in DataMiner as services.

## About

### Version Info

| **Range**            | **Key Features**                                                                   | **Based on** | **System Impact** |
|----------------------|------------------------------------------------------------------------------------|--------------|-------------------|
| 1.0.0.x              | Creating and closing tickets based on alarms generated by Ineoquest iVMS elements. | \-           | \-                |
| 1.0.1.x \[SLC Main\] | New connection to Channel API and creation of tickets with multiple services.      | 1.0.0.2      | \-                |

### Product Info

| Range     | Supported Firmware     |
|-----------|------------------------|
| 1.0.0.x   | N/A                    |
| 1.0.1.x   | N/A                    |

### System Info

| **Range** | **DCF Integration** | **Cassandra Compliant** | **Linked Components**                                                  | **Exported Components** |
|-----------|---------------------|-------------------------|------------------------------------------------------------------------|-------------------------|
| 1.0.0.x   | No                  | Yes                     | "Process Alarm Service" Automation script (see "Initialization" below) | \-                      |
| 1.0.1.x   | No                  | Yes                     | "Process Alarm Service" Automation script (see "Initialization" below) | \-                      |

## Configuration

### Connections

#### HTTP Main Connection

This connector uses an HTTP connection and requires the following input during element creation:

HTTP CONNECTION:

- **IP address/host**: The hostname of the UDO platform, e.g. *https://prepro2.udo-tt.com.*
- **IP port**: The IP port of the destination (default: *443*).

### Initialization

In order to use the **Telefonica UDO Ticketing System** connector, you must first upload the **Process Alarm Service** Automation script. For more information on how to do so, see [Importing and exporting Automation scripts](https://aka.dataminer.services/importing-and-exporting-automation-scripts).

When the script has been imported, create a Correlation rule that will execute the Automation script whenever the Ineoquest iVMS generates or clears an alarm related to the video channels. The screenshot below illustrates how to do so.

![Correlation.jpg](~/connector/images/Telefonica_UDO_Ticketing_System_Correlation.jpg)

For more information on the Correlation module, see [DataMiner Correlation](https://aka.dataminer.services/Correlation).

### Redundancy

There is no redundancy defined.

## How to use

To start using the **Telefonica UDO Ticketing System**, follow these steps:

1. On the **API Configuration** page, configure the **username** and **password** that will be used to access the UDO Platform.

1. On the **Configuration** subpage (of the **CATV Tickets** page), define the required configuration of the tickets, such as the **Fault Type**, **Severity,** etc.

1. When all information has been specified, go to the **Services** page. In the **Element** drop-down box, select the **Ineoquest iVMS element** you would like to monitor and press the **Update** button.

1. Go to the **CATV Channels** page and upload the **Channel Information** related to the iVMS element you selected. To do so:

   1. In the **Channel File Directory** box, specify the folder path where the channel CSV file is located (By default *C:\Skyline DataMiner\Documents\DMA_COMMON_DOCUMENTS\Telefonica UDO Ticketing System*).
   1. In the **CATV Channel File** drop-down box, select the name of the CSV file.
   1. Press the **Update** button.

1. Once the **CATV Channels** table is filled in, for each channel, select the respective service from the drop-down list in the **Service** column.

When you have finished the configuration, for each alarm generated by the **Ineoquest IVMS** that enters the Correlation rule's bucket, a ticket will be created in UDO. The connector will register the new ticket in the **Tickets** table of the **CATV Tickets** page.

When the alarm is cleared, the Correlation rule will be triggered again, and the ticket will be closed (the status of the ticket will be updated in the table).

If there is an issue during the creation or closing of a ticket, the status of the ticket in the table will be updated.

By default, the tickets that have had an error are removed from the Ticket table every 24 hours. You can change this interval with the **Removal Failed Tickets Time Interval** parameter.

### Range 1.0.1.x

This range introduces a change to where the **CATV Channels** information comes from. It allows you to choose between the **CSV** source and **API** source. If you choose CSV, the process continues in the same way as in the 1.0.0.x range. If you choose API as the source of the information, additional configuration is needed in a new section on the CATV Channels page called **Channel API Configuration**. You will need to enter the **token** there to establish the connection with the API. Just below that, a parameter indicates the **API Request State**.

This range also introduces the possibility to choose elements that run the **Ineoquest iVMS ASM** connector. This means that the following change to the Correlation rule is needed:

![Alarm filter configuration](~/connector/images/Telefonica_UDO_Ticketing_System_Captura_de_pantalla_2021-10-19_174320.png)

You can also disable the Correlation rule that creates and closes the tickets, in order to do this manually instead. For this purpose, you need to save a **HyperLinks.xml** file in the *C:\Skyline DataMiner* folder and add the Automation script **Update Manual UDO Ticket** on the DMA. After that, you just have to right-click the corresponding alarm and select **Ticket UDO** \> **Create/Close UDO Ticket** as shown in the image below.

![Ticket UDO menu](~/connector/images/Telefonica_UDO_Ticketing_System_Captura_de_pantalla_2021-10-20_134522.png)
