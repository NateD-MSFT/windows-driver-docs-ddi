---
UID: NC.ntddk.PSHED_PI_FINALIZE_ERROR_RECORD
title: PSHED_PI_FINALIZE_ERROR_RECORD
author: windows-driver-content
description: A PSHED plug-in's FinalizeErrorRecord callback function adds supplementary error record sections to an error record that more fully describe the error condition.
old-location: whea\finalizeerrorrecord.htm
old-project: whea
ms.assetid: 68461243-ddf4-4883-84d2-4c105f1634b2
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
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
req.alt-api: FinalizeErrorRecord
req.alt-loc: Ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= HIGH_LEVEL (See Remarks section)
---

# PSHED_PI_FINALIZE_ERROR_RECORD callback



## -description
A PSHED plug-in's <i>FinalizeErrorRecord</i> callback function adds supplementary error record sections to an error record that more fully describe the error condition.



## -prototype

````
PSHED_PI_FINALIZE_ERROR_RECORD FinalizeErrorRecord;

NTSTATUS FinalizeErrorRecord(
  _Inout_opt_ PVOID                         PluginContext,
  _In_        PWHEA_ERROR_SOURCE_DESCRIPTOR ErrorSource,
  _In_        ULONG                         BufferLength,
  _Inout_     PWHEA_ERROR_RECORD            ErrorRecord
)
{ ... }
````


## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the <b>Context</b> member of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure when the PSHED plug-in called the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED.


### -param ErrorSource [in]

A pointer to a <a href="whea.whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that reported the hardware error.


### -param BufferLength [in]

The size, in bytes, of the buffer pointed to by the <i>ErrorRecord</i> parameter.


### -param ErrorRecord [in, out]

A pointer to a <a href="whea.whea_error_record">WHEA_ERROR_RECORD</a> structure that describes the error record that is being updated with supplementary error record sections.


## -returns
A PSHED plug-in's <i>FinalizeErrorRecord</i> callback function returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The error record was successfully updated with any supplementary error record sections.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The size of the buffer pointed to by the <i>ErrorRecord </i>parameter as specified by the <i>BufferLength </i>parameter is too small to contain the error record if it is updated with the supplementary error record sections.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The PSHED plug-in does not support the specified error source.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>An error occurred.

 


## -remarks
A PSHED plug-in that participates in error information retrieval sets the <b>Callbacks.RetrieveErrorInfo</b>, <b>Callbacks.FinalizeErrorRecord</b>, and <b>Callbacks.ClearErrorStatus</b> members of the <a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a> structure to point to its <a href="..\ntddk\nc-ntddk-pshed_pi_retrieve_error_info.md">RetrieveErrorInfo</a>, <i>FinalizeErrorRecord</i>, and <a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_status.md">ClearErrorStatus</a> callback functions when the plug-in calls the <a href="whea.pshedregisterplugin">PshedRegisterPlugin</a> function to register itself with the PSHED. The PSHED plug-in must also set the <b>PshedFAErrorInfoRetrieval</b> flag in the <b>FunctionalAreaMask</b> member of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

The Windows kernel calls into the PSHED so that it can add supplementary error record sections to an error record. If a PSHED plug-in is registered to participate in error information retrieval, the PSHED calls the PSHED plug-in's <i>FinalizeErrorRecord</i> callback function so that the PSHED plug-in can add any additional error record sections to the error record that more fully describe the error condition.

A PSHED plug-in must ensure that it does not add supplementary error record sections beyond the end of the error record. The amount of memory that the Windows kernel allocates for a buffer to contain a particular error record is calculated from the <b>MaxRawDataLength</b> and <b>MaxSectionsPerRecord</b> members of the <a href="whea.whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure that describes the error source that reported the hardware error. If a PSHED plug-in requires additional buffer space to contain the supplementary error record sections that it adds to the error record, it must participate in error source discovery and increase the value in the <b>MaxSectionsPerRecord</b> member of the <b>WHEA_ERROR_SOURCE_DESCRIPTOR</b> structure for each error source as appropriate to account for any supplementary error record sections.

The PSHED calls a PSHED plug-in's <i>FinalizeErrorRecord</i> callback function at IRQL &lt;= HIGH_LEVEL. The exact IRQL at which this callback function is called depends on the specific type of hardware error that occurred.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.


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
IRQL

</th>
<td width="70%">
&lt;= HIGH_LEVEL (See Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="whea.pshedregisterplugin">PshedRegisterPlugin</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_clear_error_status.md">ClearErrorStatus</a>
</dt>
<dt>
<a href="..\ntddk\nc-ntddk-pshed_pi_retrieve_error_info.md">RetrieveErrorInfo</a>
</dt>
<dt>
<a href="whea.whea_error_record">WHEA_ERROR_RECORD</a>
</dt>
<dt>
<a href="whea.whea_error_source_descriptor">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="whea.whea_pshed_plugin_registration_packet">WHEA_PSHED_PLUGIN_REGISTRATION_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20PSHED_PI_FINALIZE_ERROR_RECORD callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
