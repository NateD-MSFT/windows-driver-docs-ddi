---
UID: NE.ntddrilapitypes.RILCONFPARTICIPANTSTATUSPARAMMASK
title: RILCONFPARTICIPANTSTATUSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilconfparticipantstatusparammask.htm
old-project: netvista
ms.assetid: a168b84a-fb3b-4e03-bb28-888b80cca6c6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILCONFPARTICIPANTSTATUSPARAMMASK, RILCONFPARTICIPANTSTATUSPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCONFPARTICIPANTSTATUSPARAMMASK
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

# RILCONFPARTICIPANTSTATUSPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILCONFPARTICIPANTSTATUSPARAMMASK { 
  RIL_PARAM_CPS_ID,
  RIL_PARAM_CPS_CALLTRANSFER,
  RIL_PARAM_CPS_ADDRESS,
  RIL_PARAM_CPS_PARTICIPANTOP,
  RIL_PARAM_CPS_SIPSTATUS,
  RIL_PARAM_CPS_ALL
} RILCONFPARTICIPANTSTATUSPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_CPS_ID


### -field RIL_PARAM_CPS_CALLTRANSFER


### -field RIL_PARAM_CPS_ADDRESS


### -field RIL_PARAM_CPS_PARTICIPANTOP


### -field RIL_PARAM_CPS_SIPSTATUS


### -field RIL_PARAM_CPS_ALL


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