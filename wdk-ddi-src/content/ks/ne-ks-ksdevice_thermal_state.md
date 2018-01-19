---
UID : NE:ks.KSDEVICE_THERMAL_STATE
title : KSDEVICE_THERMAL_STATE
author : windows-driver-content
description : A KS-defined enumeration for thermal state changes.
old-location : stream\ksdevice_thermal_state.htm
old-project : stream
ms.assetid : 37425A71-D242-4E4B-9EE8-57207A022459
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSDEVICE_THERMAL_STATE, KSDEVICE_THERMAL_STATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ks.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSDEVICE_THERMAL_STATE
req.alt-loc : ks.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : KSDEVICE_THERMAL_STATE
---

# KSDEVICE_THERMAL_STATE Enumeration
A KS-defined enumeration for thermal state changes.

## Syntax
````
typedef enum  { 
  KSDEVICE_THERMAL_STATE_LOW,
  KSDEVICE_THERMAL_STATE_HIGH
} KSDEVICE_THERMAL_STATE;
````

## Constants

<table>

<tr>
<td>KSDEVICE_THERMAL_STATE_HIGH</td>
<td>This represents the HIGH value for thermal notifications. This is usually determined by the Avstream driver and conveyed to KS in response to the thermal notification callbacks.</td>
</tr>

<tr>
<td>KSDEVICE_THERMAL_STATE_LOW</td>
<td>This represents the LOW value for thermal notifications. This is usually determined by the Avstream driver and conveyed to KS in response to the thermal notification callbacks.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |