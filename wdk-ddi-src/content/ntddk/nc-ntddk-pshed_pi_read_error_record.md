---
UID: NC:ntddk.PSHED_PI_READ_ERROR_RECORD
title: PSHED_PI_READ_ERROR_RECORD
author: windows-driver-content
description: A PSHED plug-in's ReadErrorRecord callback function reads an error record from the system's persistent data storage.
old-location: whea\readerrorrecord.htm
old-project: whea
ms.assetid: 2fcbdfe3-bcce-4e5b-a16b-501612975e82
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PSHED_PI_READ_ERROR_RECORD, ReadErrorRecord, ReadErrorRecord callback function [WHEA Drivers and Applications], ntddk/ReadErrorRecord, whea.readerrorrecord, whearef_ec353a58-1ca7-4356-8651-52802d855582.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ntddk.h
api_name:
-	ReadErrorRecord
product:
- Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---

# PSHED_PI_READ_ERROR_RECORD callback


## -description


A PSHED plug-in's <i>ReadErrorRecord </i>callback function reads an error record from the system's persistent data storage.


## -parameters




### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param Flags [in]

A bit-wise OR'ed combination of flags that affect the read operation. No flags are currently defined.


### -param ErrorRecordId [in]

The identifier of the error record to be read from the system's persistent data storage. If there is not an error record stored in the system's persistent data storage that matches this identifier, the <i>ReadErrorRecord</i> callback function must return STATUS_OBJECT_NOT_FOUND.


### -param NextErrorRecordId [out]

A pointer to a ULONGLONG-typed variable that receives the identifier of the next error record that is stored in the system's persistent data storage. If there are no other error records stored in the system's persistent data storage, the identifier for the error record that is currently being read should be returned in this parameter.


### -param RecordLength [in, out]

A pointer to a ULONG-typed variable that contains the size, in bytes, of the buffer pointed to by the <i>ErrorRecord</i> parameter. If the size of the buffer is large enough to contain the error record that is being read, the <i>ReadErrorRecord</i> callback function sets this variable to the size, in bytes, of the error record that is returned in the buffer. However, if the size of the buffer is too small to contain the error record that is being read, the <i>ReadErrorRecord</i> callback function sets this variable to the size, in bytes, that is required to contain the error record. In this situation the <i>ReadErrorRecord</i> callback function must return STATUS_BUFFER_TOO_SMALL.


### -param ErrorRecord [out]

A pointer to a buffer that receives the error record that is read from the system's persistent data storage.


## -returns



A PSHED plug-in's <i>ReadErrorRecord</i> callback function returns one of the following NTSTATUS codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The error record was successfully read from the system's persistent data storage.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
There is no error record in the system's persistent data storage that matches the identifier specified in the <i>ErrorRecordId</i> parameter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The size of the buffer is too small to contain the error record that is being read.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
An error occurred.

</td>
</tr>
</table>
 




## -remarks



A PSHED plug-in that participates in error record persistence sets the <b>Callbacks.WriteErrorRecord</b>, <b>Callbacks.ReadErrorRecord </b>and <b>Callbacks.ClearErrorRecord </b>members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="https://msdn.microsoft.com/4800a0f9-29ee-4631-aee8-5a4924a08f55">WriteErrorRecord</a>, <i>ReadErrorRecord,</i> and <a href="https://msdn.microsoft.com/e9893f9c-7fbd-4a02-8c2d-d7c480ed5198">ClearErrorRecord</a> callback functions when the plug-in calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorRecordPersistence</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED to read an error record from the system's persistent data storage after the system is restarted following a fatal or otherwise unrecoverable error condition. If a PSHED plug-in is registered to participate in error record persistence, the PSHED calls the PSHED plug-in's <i>ReadErrorRecord</i> callback function to perform the read operation. The mechanism that is used to read the error record from the system's persistent data storage is platform-specific.




## -see-also




<a href="https://msdn.microsoft.com/e9893f9c-7fbd-4a02-8c2d-d7c480ed5198">ClearErrorRecord</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559466">PshedRegisterPlugin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560483">WHEA_ERROR_RECORD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560617">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>



<a href="https://msdn.microsoft.com/4800a0f9-29ee-4631-aee8-5a4924a08f55">WriteErrorRecord</a>
 

 

