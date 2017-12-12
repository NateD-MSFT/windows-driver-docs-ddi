---
UID: NF.ntddk.PsDereferenceSiloContext
title: PsDereferenceSiloContext function
author: windows-driver-content
description: This routine decrements the reference count on the object.
old-location: kernel\psdereferencesilocontext.htm
old-project: kernel
ms.assetid: B71C7E8F-E136-4C13-B771-03B3C3C1BE64
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PsDereferenceSiloContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsDereferenceSiloContext
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _IRQL_requires_max_(DISPATCH_LEVEL)
---

# PsDereferenceSiloContext function



## -description
This routine decrements the reference count on the object.



## -syntax

````
void PsDereferenceSiloContext(
  _In_ PVOID SiloContext
);
````


## -parameters

### -param SiloContext [in]

A pointer to the object created by the <a href="kernel.pscreatesilocontext">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>. 


## -returns
This routine does not return a value.


## -remarks
If the reference count reaches zero it will call the cleanup callback provided when the <a href="kernel.pscreatesilocontext">PsCreateSiloContext</a> routine created the object. 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1607

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
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
_IRQL_requires_max_(DISPATCH_LEVEL)

</td>
</tr>
</table>