---
uid: EPM_1.0.3_VSAT
---

# EPM 1.0.3 VSAT - Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

## New features

#### Verizon iDirect Evolution Platform Collector: Hub Return Network column added to Linecard Table [ID_36566]

In the Verizon iDirect Evolution Platform Collector connector, a new Hub Return Network column has been added to the Linecard Table, between the Hub Forward Network and Name[IDX] columns.

#### Verizon iDirect Evolution Platform Collector: New and updated ATDMA carrier parameters [ID_36567]

In the Verizon iDirect Evolution Platform Collector connector, the following columns/KPIs have been added to the Hub Return Overview and Carrier Table:

- *Active ICG ID*: Active composition group ID based on the current active composition group, which can vary with ATDMA carriers.
- *Active ICG FM*: Active composition group figure of merit based on the current active composition group, which can vary with ATDMA carriers.
- *Payload*: Payload size in bytes.
- *Target C/No*: Calculated target C/No based on the current active composition group and carrier.

In addition, the following parameters have been updated:

- *Fecrate*: Current FEC rate based on the current active composition group and carrier.
- *Modulation Name*: Current modulation based on the current active composition group and carrier.
- *Carrier Type*: The type of carrier.

#### New Circuit Availability KPI [ID_36900]

A new Circuit Availability KPI is now available in the Verizon iDirect Evolution Platform and Verizon VSAT Platform Manager connectors. This KPI, which can be found in the Circuit Overview table, shows a percentage indicating how close circuit performance tracks against the theoretical link budget expectations. The KPI is aggregated by average in the Circuit level, Hub Forward level, Hub Return level, Customer level, and NMS level of the EPM topology.

## Changes

### Enhancements

#### iDirect Evolution Platform Collector: MODCOD reference for hub return carriers updated [ID_36471]

The MODCOD reference for hub return carriers has been updated.

#### Generic Sun Outage: Outages Table primary key changed from string to integer-based values [ID_36565]

In the Generic Sun Outage connector, the primary key of the Outages Table (parameter ID 600) now uses integer-based values instead of string values. The values consist of the ID concatenated with the epoch time of the start of the outage.

#### Verizon WM Ticketing: Improved weather recheck logic and location metrics [ID_36931]

The logic for weather rechecks in the Verizon WM Ticketing connector has been adjusted, so that these are now performed in batches instead of one by one. In addition, location values of circuits will now be retrieved from the circuit information in real time.

#### Verizon VSAT Platform Manager: Improved logic to export location metrics of circuits [ID_36932]

The logic in the Verizon VSAT Platform Manager connector to export location metrics of circuits to the topology file has been improved.

#### Verizon iDirect Evolution Platform Collector: Improved logic to export location metrics of circuits [ID_36934]

The logic in the Verizon iDirect Evolution Platform Collector connector to export location metrics of circuits to the exported circuit files has been improved.

#### Verizon ETMS Platform: Improved weather recheck logic [ID_36935]

The logic for weather rechecks in the Verizon ETMS Platform connector has been adjusted, so that these are now performed in batches instead of one by one.

#### Verizon ETMS Platform: Improved description in case there are failed KPIs but no power issues [ID_36937]

In the Verizon ETMS Platform connector, the description when there are failed KPIs but no power issues has been updated to "Further Investigation Required".

#### Verizon WM Ticketing: Improved description in case there are failed KPIs but no power issues [ID_36937]

In the Verizon WM Ticketing connector, the description when there are failed KPIs but no power issues has been updated to "Further Investigation Required".

#### Carrier performance scripts improvements [ID_36957] [ID_36958] [ID_36959] [ID_36960] [ID_36961]

The *GQIO_Percentage_Double*, *GQIO_Percentage_Int*, *GQIO_MultiplyByPercentage*, *GQIO_RunningTotal_Double*, and *GQIO_RunningTotal_Int* scripts have been updated as follows:

- The *Folder* XML tag has been added to each script, so that it is placed in the *CARRIER PERFORMANCE* Automation folder by default.
- The *preCompile* and *libraryName* XML tags have also been added to each script, so that it is compiled as a library and given a library name by default, making it visible in the Dashboards app.

### Fixes

#### Verizon iDirect Evolution Platform Collector: BUC Table empty [ID_36640]

Elements using the Verizon iDirect Evolution Platform Collector connector did not show any information in the BUC Table.

#### Verizon iDirect Evolution Platform Collector: Current state not indicated in Remotes Overview tables [ID_36673]

In the Remotes Overview tables of Verizon iDirect Evolution Platform Collector elements, the *Current State* column could incorrectly show "Not initialized".
