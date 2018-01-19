---
UID : NE:usbfnbase._USBFN_DIRECTION
title : _USBFN_DIRECTION
author : windows-driver-content
description : Defines the USB data transfer direction types.
old-location : buses\usbfn_direction.htm
old-project : usbref
ms.assetid : C6E1FA5A-993C-4212-9428-0B759C09F5DE
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USBFN_DIRECTION, *PUSBFN_DIRECTION, USBFN_DIRECTION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : usbfnbase.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : USBFN_DIRECTION
req.alt-loc : usbfnbase.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PUSBFN_DIRECTION, USBFN_DIRECTION"
req.product : Windows 10 or later.
---

# _USBFN_DIRECTION Enumeration
Defines the USB data transfer direction types.

## Syntax
````
typedef enum _USBFN_DIRECTION { 
  UsbfnDirectionMinimum  = 0x0,
  UsbfnDirectionIn,
  UsbfnDirectionOut,
  UsbfnDirectionTx       = UsbfnDirectionIn,
  UsbfnDirectionRx       = UsbfnDirectionOut,
  UsbfnDirectionMaximum
} USBFN_DIRECTION;
````

## Constants

<table>

<tr>
<td>UsbfnDirectionIn</td>
<td>The transfer is to the host from an endpoint.</td>
</tr>

<tr>
<td>UsbfnDirectionMaximum</td>
<td>The maximum value in this enumeration.</td>
</tr>

<tr>
<td>UsbfnDirectionMinimum</td>
<td>The minimum value in this enumeration.</td>
</tr>

<tr>
<td>UsbfnDirectionOut</td>
<td>The transfer is from the host to the endpoint.</td>
</tr>

<tr>
<td>UsbfnDirectionRx</td>
<td>The bus transfer is from the host to the device.</td>
</tr>

<tr>
<td>UsbfnDirectionTx</td>
<td>The bus transfer to the host from the device.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbfnbase.h |