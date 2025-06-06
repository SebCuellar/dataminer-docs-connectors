---
uid: Connector_help_Axon_ACP_-_GFT80
---

# Axon ACP - GFT80

The GFT80 is a 3 Gb/S, HD and SD 8-channel electrical to optical converter with full fiber diagnostics and hot-swappable fiber modules (ASI/DVB compatible).

The **Axon ACP - GFT80** connector can be used to display and configure information related to this device.

## About

This connector is automatically generated by the connector **Axon ACP**.

There are different possibilities available for **alarm monitoring** and **trending**.

### Version Info

| Range     | Description                        | DCF Integration     | Cassandra Compliant     |
|------------------|------------------------------------|---------------------|-------------------------|
| 1.0.2.x          | Change in export rules.            | Yes                 | Yes                     |
| 1.0.3.x          | Change in discrete display values. | Yes                 | Yes                     |

### Product Info

| Range | Supported Firmware Version |
|------------------|-----------------------------|
| 1.0.2.x          | 0701                        |
| 1.0.3.x          | 701                         |

## Installation and configuration

### Creation

This element is automatically created by the parent element using the **Axon ACP** connector.

## Usage

This element has the following data pages:

- **General**: This page displays general information about the card: **Card Name**, **Card Description**, **SW Revision**, **HW Revision**, etc.
- **SFP 1**
- **SFP 2**
- **SFP 3**
- **SFP 4**
- **Status**
- **Settings**
- **Alarm Priority**: This page displays the event messages of the card, i.e. special messages generated asynchronously on the card.

## DataMiner Connectivity Framework

The Axon ACP connector supports the usage of DCF.

DCF can also be implemented through the DataMiner DCF user interface and through DataMiner third-party connectors (for instance a manager).

Connectivity for this protocol is managed by the parent protocol Axon ACP.

### Interfaces

#### Physical Interfaces

- **SDI Input 1**: A single fixed interface of type **input**.
- **SDI Input 2**: A single fixed interface of type **input**.
- **SDI Input 3**: A single fixed interface of type **input**.
- **SDI Input 4**: A single fixed interface of type **input**.
- **SDI Input 5**: A single fixed interface of type **input**.
- **SDI Input 6**: A single fixed interface of type **input**.
- **SDI Input 7**: A single fixed interface of type **input**.
- **SDI Input 8**: A single fixed interface of type **input**.
- **FIBER Output 1**: A single fixed interface of type **output**.
- **FIBER Output 2**: A single fixed interface of type **output**.
- **FIBER Output 3**: A single fixed interface of type **output**.
- **FIBER Output 4**: A single fixed interface of type **output**.
- **FIBER Output 5**: A single fixed interface of type **output**.
- **FIBER Output 6**: A single fixed interface of type **output**.
- **FIBER Output 7**: A single fixed interface of type **output**.
- **FIBER Output 8**: A single fixed interface of type **output**.
