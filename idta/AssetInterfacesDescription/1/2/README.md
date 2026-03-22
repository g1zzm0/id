# Asset Interfaces Description – Identifiers

This Submodel specifies an information model and a common representation for describing the interface(s) of an asset service or asset-related service. Based on this information, it is possible to initiate a connection to such a service and start to request or subscribe to served datapoints, and/or perform operations



## Introduction

The Asset Interfaces Description (AID) in version 1.2 supports the description of interfaces based on the following specific protocols: 
* Modbus
* HTTP
* MQTT
* OPC UA
* BACnet
* IO-Link
* SNMP
* CAN
  
Informative, the IO-Link protocol that is bridged to REST/HTTP and PROFINET is introduced in AID 1.2 in Annex B. Any other protocols and interfaces will be addressed in upcoming versions of the AID. 
The W3C Web of Things Thing Description (WoT TD) as an open, royalty-free standard is considered as a baseline for the content and structure of the definition of this Submodel template. The protocol-specific information is taken from the official WoT bindings that are maintained by the W3C or other SDOs like the OPC Foundation (e.g., OPC 10101 for OPC UA Binding).  
In addition to the protocol-specific information provided by the AID, it also provides the ability to reference external descriptors such as GSD, GSDML, IO Device Description, native WoT TD (as a supplement), etc. These external descriptors are not restricted to the protocols currently defined in AID.
As a complement to the AID, an Asset Interfaces Mapping Configuration (AIMC) Submodel can be used to map the received data from the asset services to a specific place within an AAS (e.g., an application-specific Submodel to monitor data). The principal scope and use of the AID Submodel in combination with an AIMC 



## Status: `Accepted`
The sub-namespace for Asset Interface Description and its identifiers have been finalized in the Taskforce `Asset Interface Description`.

## Versions: 1.2
This version is the third version to be officially published by IDTA Document `IDTA 02017 Asset Interfaces Description`.

## SNMP (SMC)
SNMP Specific Identifier

https://admin-shell.io/idta/AssetInterfacesDescription/1/2/SNMP

## CAN (SMC)

CAN specific identifiers
https://admin-shell.io/idta/AssetInterfacesDescription/1/2/CAN

### canv_offset (Property)
Offset to indicate the beginning of a data point in the message payload. Must be in the range [0, 63].
https://admin-shell.io/idta/AssetInterfacesDescription/1/2/CAN/offset

### canv_length (Property)
Length of the data point in the message payload. Must be in the range [1, 64].
https://admin-shell.io/idta/AssetInterfacesDescription/1/2/CAN/length

### canv_valueOffset (Property)
A constant to add to the decoded data point in order to restore its actual value. “valueType” must match the "property_name.type" field.
https://admin-shell.io/idta/AssetInterfacesDescription/1/2/CAN/value-offset


## Interface supplementalSemanticIds





## Contact

This sub-namespace is proposed by [IDTA Working Group Nameplate for Asset Interface Description](https://github.com/admin-shell-io/submodel-templates/tree/main/published/Asset%20Interfaces%20Description). 
See also [IDTA Registered AAS Submodel Templates](https://industrialdigitaltwin.org/content-hub/teilmodelle#:~:text=Software%20Nameplate) or contact via email the [IDTA project manager for submodel templates](mailto:sudip.adhikari@idtwin.org) or [chair of the working group](mailto:sebastian.kaebisch@siemens.com).

