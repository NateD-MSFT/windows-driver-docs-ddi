---
UID: NF.ntddk.IoSetSystemPartition
title: IoSetSystemPartition function
author: windows-driver-content
description: The IoSetSystemPartition routine sets the boot partition for the system.
old-location: kernel\iosetsystempartition.htm
old-project: kernel
ms.assetid: f1606881-da8b-4034-bbdf-53c75e594032
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: IoSetSystemPartition
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetSystemPartition
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
---

# IoSetSystemPartition function



## -description
The <b>IoSetSystemPartition</b> routine sets the boot partition for the system.



## -syntax

````
NTSTATUS IoSetSystemPartition(
  _In_ PUNICODE_STRING VolumeNameString
);
````


## -parameters

### -param VolumeNameString [in]

Pointer to a Unicode string that specifies the MS-DOS name of the system partition. 


## -returns
STATUS_SUCCESS if the boot partition can be set, or an error code on failure. 


## -remarks
The specified partition must contain the boot loader.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows XP and later versions of Windows. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>