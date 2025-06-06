---
uid: Connector_help_Axon_ACP_HXH40
---

# Axon ACP HXH40

The HXH40 is an HD up-/down-/cross- & standards converter.

The **Axon ACP HXH40** connector can be used to display and configure information related to this device.

## About

This connector can be automatically generated by the connector **Axon ACP**.

There are different possibilities available for **alarm monitoring** and **trending**.

### Version Info

| Range     | Key Features                 | Based on     | System Impact     |
|-----------|------------------------------|--------------|-------------------|
| 1.0.0.x   | Initial version [SLC Main]   | -            | -                 |

### Product Info

| Range     | Supported Firmware     |
|-----------|------------------------|
| 1.0.0.x   | 1824, 1926             |

### System Info

| Range     | DCF Integration     | Cassandra Compliant     | Linked Components     | Exported Components     |
|-----------|---------------------|-------------------------|-----------------------|-------------------------|
| 1.0.0.x   | Yes                 | Yes                     | -                     | -                       |

## Installation and configuration

### Creation

The element using this connector can be automatically created by the parent element using the **Axon ACP** connector, but it can also be a standalone element.

### Connections

#### Serial Main Connection

This connector uses a serial connection and requires the following input during element creation:

SERIAL CONNECTION:

- Interface connection:

  - **IP address/host**: The polling IP or URL of the destination.
  - **Bus address**: The bus address of the device, being the slot number of the card.

#### Serial Broadcast Connection

This connector uses a serial connection and requires the following input during element creation:

SERIAL CONNECTION:

- Interface connection:

  - **IP address/host**: The polling IP or URL of the destination.
  - **Bus address**: The bus address of the device.

## Usage

This element has the following data pages:

- **General**: This page displays general information about the card: **Card Name**, **Card Description**, **SW Revision**, **HW Revision**, etc.
- **Status**
- **Audio Status**
- **I/O**
- **Video**
- **Audio**
- **Embedder**
- **Settings**
- **Up Conversion**
- **Down Conversion**
- **Cross Conversion**
- **Standard Conversion**
- **Alarm Priority**: This page displays the event messages of the card, i.e. special messages generated asynchronously on the card.

## DataMiner Connectivity Framework

The Axon ACP connector supports the usage of DCF.

DCF can also be implemented through the DataMiner DCF user interface and through DataMiner third-party connectors (for instance a manager).

### Interfaces

#### Physical Interfaces

- **SDI Input**: A single fixed interface of type **input**.
- **REF Input 1**: A single fixed interface of type **input**.
- **REF Input 2**: A single fixed interface of type **input**.
- **SDI Output 1**: A single fixed interface of type **output**.
- **SDI Output 2**: A single fixed interface of type **output**.
- **SDI Reclocked Output**: A single fixed interface of type **output**.
- **SYNAPSE Bus 1**: A single fixed interface of type **output**.
- **SYNAPSE Bus 2**: A single fixed interface of type **output**.
- **SYNAPSE Bus 3**: A single fixed interface of type **output**.
- **SYNAPSE Bus 4**: A single fixed interface of type **output**.

### Connections

#### Internal Connections

When a DVE child element is created, the following connections are established:

- **SDI Input** and **SDI Output 1**.
- Between **SDI Input** and **SDI Output 2**.
- Between **SDI Input** and **SDI Reclocked Output**.
- Between **SDI Input** and **SYNAPSE Bus 1**.
- Between **SDI Input** and **SYNAPSE Bus 2**.
- Between **SDI Input** and **SYNAPSE Bus 3**.
- Between **SDI Input** and **SYNAPSE Bus 4**.

Depending on the state of the **Reference Input**, the following connections are established:

- **1**:

- Between **REF Input 1** and **SDI Output 1**.
  - Between **REF Input 1** and **SDI Output 2**.

- **2**:

- Between **REF Input 2** and **SDI Output 1**.
  - Between **REF Input 2** and **SDI Output 2**.
