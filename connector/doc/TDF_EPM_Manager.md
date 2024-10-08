---
uid: Connector_help_TDF_EPM_Manager
---

# TDF EPM Manager

The **TDF EPM Manager** connector is an Experience and Performance Management connector, and as such it is designed to handle large amounts of data from the deployed infrastructures. It manages and monitors devices across various Equipment Management Systems (EMSs), maintaining relational data and aggregating data that can be viewed through a central front-end interface and the DataMiner Topology app.

A deployed EPM Solution consists of one TDF EPM Manager front-end element and can have one or multiple back-end elements (using the same connector). The TDF EPM Manager front-end element is responsible for top-level data aggregation from different back-end elements. Each back-end element handles data aggregation from the collectors.

The geographical topology is presented in the TDF EPM Manager and represents a connected entity from top to bottom:

- **Geographical**

  - Zone
  - Department
  - Site
  - Equipment

- **Configuration**

  - Allows you to place Visual Overview layouts on a separate chain.

## About

### Version Info

| Range              | Features        | Based on | System Impact |
|--------------------|-----------------|----------|---------------|
| 1.0.0.x [SLC Main] | Initial version | -        | -             |

### System Info

| Range   | DCF Integration | Cassandra Compliant | Linked Components | Exported Components |
|---------|-----------------|---------------------|-------------------|---------------------|
| 1.0.0.x | No              | Yes                 | -                 | -                   |

## Configuration

### Connections

#### Virtual Connection - Main

This connector uses a virtual connection and does not require any input during element creation.

### Initialization

When creating the managers manually, follow these steps:

1. Create a single **front-end element** and configure it as follows:

   1. On the **Configuration** page, change the **Element Manager Type** to *Frontend*.

   1. In the **Import Settings**, fill in the import directory where the provisioning files are located.

   1. In the **Export Settings**, fill in the location from which the **back-end** elements will be importing.

   1. In the **Helios Settings**, specify the import directory where Helios files, such as device and site files, are located.

1. Create as many **back-end** elements as needed.

   Typically, the front-end element should be on a DMA of its own, and there should be a back-end element on all other DMAs. If the DMS only consists of one DMA, then it can have one front-end and one back-end element.

1. In the **Import Settings** on the Configuration page of the back-end elements, fill in the directory where the front-end element will export.

1. In the **Export Settings** on the Configuration page of the back-end elements, fill in the directory from which the collectors will import.

1. In the **front-end** element, fill in the necessary DMA ID/Element IDs:

   1. In **Frontend Registration** table, fill in the DMA ID/Element ID of the front-end element.

   1. In the **Backend Registration** table, fill in all DMA ID/Element IDs of the back-end elements in the system.

   1. In the **Collector Registration** table, fill in all DMA ID/Element IDs of the collector elements in the system.

1. In the **back-end** elements, fill in the necessary DMA ID/Element IDs:

   1. In the **Backend Registration** table, fill in the DMA ID/Element ID of the current back-end element.

   1. In the **Collector Registration** table, fill in all DMA ID/Element IDs of the collector elements on the same DMA.

1. On the **Configuration** page of the front-end element, click the **Import** button to begin the provisioning.

### Redundancy

There is no redundancy defined.

## How to use

Once the EPM Manager elements are configured, the only required procedure is for the front-end element to import the following CSV files and initiate the ID assignment process:

- Zones.csv
- Departments.csv
- Sites.csv
- Device.csv (contains all devices across the EMSs that are not available in their inventories)
- Device.csv per EMS/collector (if available)

After the ID assignment is completed, the front-end element exports a series of CSVs. These files are then imported by the back-end and collector elements. To initiate this process, the front-end element notifies the respective back-end/collector element to process these files using an InterApp message.

## Notes

The front-end element creates structured files with unique IDs per entity for the back-end and collector elements. Additionally, an extra file is generated per collector, containing equipment and site-related information from the Helios DB inventory with equipment and site metadata for all service types.

This file is created based on two other files that are regularly generated by the **TDF Helios Database** connector:

- Helios DB-Equipments.csv
- Helios DB-Sites.csv
