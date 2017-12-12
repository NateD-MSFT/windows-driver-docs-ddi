---
UID: NE.wditypes._WDI_PHY_TYPE
title: _WDI_PHY_TYPE
author: windows-driver-content
description: The WDI_PHY_TYPE enumeration defines the PHY types.
old-location: netvista\wdi_phy_type.htm
old-project: netvista
ms.assetid: BDA90056-6DAA-4FC8-82EC-3062087E02C4
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WDI_PHY_TYPE, WDI_PHY_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_PHY_TYPE
req.alt-loc: wditypes.hpp
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _WDI_PHY_TYPE enumeration



## -description
The WDI_PHY_TYPE enumeration defines the PHY types.



## -syntax

````
typedef enum _WDI_PHY_TYPE { 
  WDI_PHY_TYPE_UNKNOWN     = 0,
  WDI_PHY_TYPE_ANY         = 0,
  WDI_PHY_TYPE_FHSS        = 1,
  WDI_PHY_TYPE_DSSS        = 2,
  WDI_PHY_TYPE_IRBASEBAND  = 3,
  WDI_PHY_TYPE_OFDM        = 4,
  WDI_PHY_TYPE_HRDSSS      = 5,
  WDI_PHY_TYPE_ERP         = 6,
  WDI_PHY_TYPE_HT          = 7,
  WDI_PHY_TYPE_VHT         = 8,
  WDI_PHY_TYPE_DMG         = 9,
  WDI_PHY_TYPE_IHV_START   = 0x80000000,
  WDI_PHY_TYPE_IHV_END     = 0xffffffff
} WDI_PHY_TYPE;
````


## -enum-fields

### -field WDI_PHY_TYPE_UNKNOWN

Specifies an unknown or uninitialized PHY type.


### -field WDI_PHY_TYPE_ANY

Specifies an unknown or uninitialized PHY type.


### -field WDI_PHY_TYPE_FHSS

Specifies a frequency-hopping spread-spectrum (FHSS) PHY.


### -field WDI_PHY_TYPE_DSSS

Specifies a direct sequence spread spectrum (DSSS) PHY.


### -field WDI_PHY_TYPE_IRBASEBAND

Specifies an infrared (IR) baseband PHY.


### -field WDI_PHY_TYPE_OFDM

Specifies an orthogonal frequency division multiplexing (OFDM) 802.11a PHY.


### -field WDI_PHY_TYPE_HRDSSS

Specifies a high-rate DSSS (HRDSSS) 802.11b PHY.


### -field WDI_PHY_TYPE_ERP

Specifies an extended-rate 802.11g PHY (ERP).


### -field WDI_PHY_TYPE_HT

Specifies a high-throughput (HT) 802.11n PHY. Each 802.11n PHY, whether dual-band or not, is specified as this PHY type.




### -field WDI_PHY_TYPE_VHT

Specifies a very high-throughput (VHT) 802.11ac PHY.


### -field WDI_PHY_TYPE_DMG

Added in Windows 10, version 1607, WDI version 1.0.21.

Specifies an 802.11ad PHY.


### -field WDI_PHY_TYPE_IHV_START

Specifies the start of the range that is used to define proprietary PHY types that are developed by an independent hardware vendor (IHV). 




### -field WDI_PHY_TYPE_IHV_END

Specifies the end of the range that is used to define proprietary PHY types that are developed by an IHV. 




## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>