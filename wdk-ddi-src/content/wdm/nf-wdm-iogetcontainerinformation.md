---
UID: NF.wdm.IoGetContainerInformation
title: IoGetContainerInformation function
author: windows-driver-content
description: The IoGetContainerInformation routine provides information about the current state of a user session.
old-location: kernel\iogetcontainerinformation.htm
old-project: kernel
ms.assetid: 34612bc5-bed5-4645-8619-64ae2a603d1e
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: IoGetContainerInformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoGetContainerInformation
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
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# IoGetContainerInformation function



## -description
The <b>IoGetContainerInformation</b> routine provides information about the current state of a user session. 



## -syntax

````
NTSTATUS IoGetContainerInformation(
  _In_     IO_CONTAINER_INFORMATION_CLASS InformationClass,
  _In_opt_ PVOID                          ContainerObject,
  _Inout_  PVOID                          Buffer,
  _In_     ULONG                          BufferLength
);
````


## -parameters

### -param InformationClass [in]

Specifies the class of events for which the caller (driver) requests information. Set this parameter to the following <a href="kernel.io_container_information_class">IO_CONTAINER_INFORMATION_CLASS</a> enumeration value:

<ul>
<li>
<b>IoSessionStateInformation</b>

</li>
</ul>
For more information, see the following Remarks section. 


### -param ContainerObject [in, optional]

A pointer to an opaque, system object supplied by the I/O manager. For <i>InformationClass</i> = <b>IoSessionStateInformation</b>, set this parameter to the <i>SessionObject</i> parameter value that is provided by the I/O manager during the call to the driver's <a href="..\wdm\nc-wdm-io_session_notification_function.md">IO_SESSION_NOTIFICATION_FUNCTION</a> function. 


### -param Buffer [in, out]

A pointer to a caller-allocated buffer into which this routine writes the state information for the event class specified by <i>InformationClass</i>. For <i>InformationClass</i> = <b>IoSessionStateInformation</b>, the routine writes an <a href="kernel.io_session_state_information">IO_SESSION_STATE_INFORMATION</a> structure to the buffer. The buffer must be large enough to contain this structure. 


### -param BufferLength [in]

The size, in bytes, of the buffer pointed to by <i>Buffer</i>. For <i>InformationClass</i> = IoSessionStateInformation, <i>BufferLength</i> must be at least <b>sizeof</b>(<b>IO_SESSION_STATE_INFORMATION</b>). 


## -returns
<b>IoGetContainerInformation</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>Parameter <i>InformationClass</i> is not a valid <a href="kernel.io_container_information_class">IO_CONTAINER_INFORMATION_CLASS</a> enumeration constant.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>Parameter <i>ContainerObject</i> is <b>NULL</b>.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_4</b></dt>
</dl>Parameter <i>BufferLength</i> is too small for the information class specified by <i>InformationClass</i>.

 


## -remarks
This routine can potentially support queries for a variety of information classes. In Windows 7, this routine supports only queries for <b>IoSessionStateInformation</b> information, which is status information about user sessions.


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
Available in Windows 7 and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
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
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.io_container_information_class">IO_CONTAINER_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.io_container_notification_class">IO_CONTAINER_NOTIFICATION_CLASS</a>
</dt>
<dt>
<a href="kernel.io_session_state_information">IO_SESSION_STATE_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetContainerInformation routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
