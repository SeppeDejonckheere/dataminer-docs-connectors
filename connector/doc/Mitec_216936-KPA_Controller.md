---
uid: Connector_help_Mitec_216936-KPA_Controller
---

# Mitec 216936-KPA Controller

The 216936-01 MD 1:3 redundant switch is a microcontroller-based unit designed to monitor and control a switching/combining network, consisting of:

- 4 high power amplifiers (HPA), 3 online and one on standby
- 7 waveguide switches with locks
- 4 coaxial switches
- 4 waveguide switches

It performs manual or automatic switches to backup for the system's high power amplifiers.

## About

### Version Info

| Range                | Key Features     | Based on     | System Impact     |
|----------------------|------------------|--------------|-------------------|
| 1.0.0.x \[SLC Main\] | Initial version  | \-           | \-                |

### Product Info

| **Range** | **Supported Firmware**                             |
|-----------|----------------------------------------------------|
| 1.0.0.x   | Configuration version: 1.00 Software version: 2.23 |

### System Info

| Range     | DCF Integration     | Cassandra Compliant     | Linked Components     | Exported Components     |
|-----------|---------------------|-------------------------|-----------------------|-------------------------|
| 1.0.0.x   | No                  | Yes                     | \-                    | \-                      |

## Configuration

### Connections

#### Serial Connection

This connector uses a serial connection and requires the following input during element creation:

SERIAL CONNECTION:

- Direct connection:

  - **Baudrate**: Baudrate specified in the manual of the device, e.g. *9600* (default: *9600*).
  - **Databits**: Databits specified in the manual of the device, e.g. *7* (default: *7*).
  - **Stopbits**: Stopbits specified in the manual of the device, e.g. *1* (default: *1*).
  - **Parity**: Parity specified in the manual of the device, e.g. *No* (default: *even*).
  - **FlowControl**: FlowControl specified in the manual of the device, e.g. *No* (default: *no*).

- Interface connection:

  - **IP address/host**: The polling IP or URL of the destination.
  - **IP port**: The IP port of the destination.

## How to use

The **General** page provides an overview of the device information, summary alarm status and FAN status information.

The **SW** page provides an overview of the waveguide switches. You can change the position of a switch by clicking the preferred switch position for that switch.

The **SC** page provides an overview of the coaxial switches.

The **HPA** page provides an overview of the HPAs. You can change the maintenance mode by selecting your preferred mode for the corresponding HPA.
