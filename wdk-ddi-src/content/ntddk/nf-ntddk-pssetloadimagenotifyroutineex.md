---
UID: NF.ntddk.PsSetLoadImageNotifyRoutineEx
title: PsSetLoadImageNotifyRoutineEx function
author: windows-driver-content
description: The PsSetLoadImageNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
old-location: kernel\pssetloadimagenotifyroutineex.htm
old-project: kernel
ms.assetid: 792cdb59-e0c2-4697-9934-b7e45a7a31a8
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PsSetLoadImageNotifyRoutineEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsSetLoadImageNotifyRoutineEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
---

# PsSetLoadImageNotifyRoutineEx function



## -description
The <b>PsSetLoadImageNotifyRoutineEx</b> routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).



## -syntax

````
 NTSTATUS  PsSetLoadImageNotifyRoutineEx(
  _In_ PLOAD_IMAGE_NOTIFY_ROUTINE NotifyRoutine,
  _In_ ULONG_PTR                  Flags
);
````


## -parameters

### -param NotifyRoutine [in]

A pointer to the caller-implemented <a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a> callback routine for load-image notifications.


### -param Flags [in]

Supplies a bitmask of flags that control the callback function. Here are the possible values:

<ul>
<li>PS_IMAGE_NOTIFY_CONFLICTING_ARCHITECTURE indicates that the callback routine should be invoked for all potentially executable images, including images that have a different architecture from the native architecture of the operating system.

</li>
</ul>

## -returns
<dl>
<dt><b>STATUS_SUCCESS </b></dt>
</dl>The callback was successfully registered.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>Invalid flag was supplied in <i>Flags</i>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The routine failed allocate a callback block due to lack of resources.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

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
<dt>NtosKrnl.exe (kernel mode)</dt>
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