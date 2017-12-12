---
UID: NF.fwpsk.FwpsvSwitchNotifyComplete0
title: FwpsvSwitchNotifyComplete0 function
author: windows-driver-content
description: The FwpsvSwitchNotifyComplete0 function completes a pending virtual switch event notification.Note  FwpsvSwitchNotifyComplete0 is a specific version of FwpsvSwitchNotifyComplete.
old-location: netvista\fwpsvswitchnotifycomplete0.htm
old-project: netvista
ms.assetid: 5e40a31f-7730-48f0-899f-f59be654c991
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: FwpsvSwitchNotifyComplete0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FwpsvSwitchNotifyComplete0
req.alt-loc: fwpkclnt.lib,fwpkclnt.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FwpsvSwitchNotifyComplete0 function



## -description
The <b>FwpsvSwitchNotifyComplete0</b> function completes a pending virtual switch event notification.<div class="alert"><b>Note</b>  <b>FwpsvSwitchNotifyComplete0</b> is a specific version of <b>FwpsvSwitchNotifyComplete</b>. See <a href="fwp.wfp_version-independent_names_and_targeting_specific_versions_of_windows">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div>
<div> </div>




## -syntax

````
void NTAPI FwpsvSwitchNotifyComplete0(
   _In_ void              *completionContext,
   _In_ NTSTATUS          status,
   _In_ _Reserved_ UINT32 flags,
   _In_ _Reserved_ void   *reserved
);
````


## -parameters

### -param completionContext 

The context data that was  passed to the callback driver from the virtual switch event notify function.


### -param status 

Any NTSTATUS value that is a valid return code for the notification that was pending completion except for STATUS_PENDING.


### -param flags 

Reserved. Set this member to zero.


### -param reserved 

Reserved. Set this member to zero.


## -returns
None.


## -remarks

    If a callout driver returns STATUS_PENDING from a WFP notification function, WFP will return STATUS_PENDING for any associated OID request. The callout  driver calls the <b>FwpsvSwitchNotifyComplete0</b> function to complete the pending operation. After the <b>FwpsvSwitchNotifyComplete0</b> call, WFP calls the  <a href="netvista.ndisfoidrequestcomplete">NdisFOidRequestComplete</a> function to complete the OID for  the virtual switch.
   


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
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Fwpkclnt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a>
</dt>
<dt>
<a href="netvista.fwpscompleteclassify0">FwpsCompleteClassify0</a>
</dt>
<dt>
<a href="netvista.ndisfoidrequestcomplete">NdisFOidRequestComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsvSwitchNotifyComplete0 function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
