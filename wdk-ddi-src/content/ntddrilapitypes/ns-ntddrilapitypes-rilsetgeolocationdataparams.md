---
UID: NS.NTDDRILAPITYPES.RILSETGEOLOCATIONDATAPARAMS
title: RILSETGEOLOCATIONDATAPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetgeolocationdataparams.htm
old-project: netvista
ms.assetid: 7736c8d6-731e-4322-aade-ecd23a4fedde
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILSETGEOLOCATIONDATAPARAMS, *LPRILSETGEOLOCATIONDATAPARAMS, RILSETGEOLOCATIONDATAPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSETGEOLOCATIONDATAPARAMS
req.alt-loc: ntddrilapitypes.h
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
---

# RILSETGEOLOCATIONDATAPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSETGEOLOCATIONDATAPARAMS {
  DWORD                 cbSize;
  DWORD                 dwExecutor;
  RILOSGEOLOCATIONINFO  locationInfo;
} RILSETGEOLOCATIONDATAPARAMS, RILSETGEOLOCATIONDATAPARAMS;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field locationInfo


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>