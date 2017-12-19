---
UID: NF.wudfusb.IWDFUsbTargetPipe.RetrievePipePolicy
title: IWDFUsbTargetPipe::RetrievePipePolicy method
author: windows-driver-content
description: The RetrievePipePolicy method retrieves a WinUsb pipe policy.
old-location: wdf\iwdfusbtargetpipe_retrievepipepolicy.htm
old-project: wdf
ms.assetid: 578f7633-307e-4cda-b8fe-ae73a095976f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFUsbTargetPipe, IWDFUsbTargetPipe::RetrievePipePolicy, RetrievePipePolicy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFUsbTargetPipe.RetrievePipePolicy
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.product: Windows 10 or later.
---

# IWDFUsbTargetPipe::RetrievePipePolicy method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrievePipePolicy</b> method retrieves a WinUsb pipe policy.



## -syntax

````
HRESULT RetrievePipePolicy(
  [in]      ULONG PolicyType,
  [in, out] ULONG *ValueLength,
  [out]     PVOID Value
);
````


## -parameters

### -param PolicyType [in]

The type of WinUsb pipe policy that the UMDF driver requests.


### -param ValueLength [in, out]

A pointer to a variable that, on input, contains the size, in bytes, of the buffer that <b>RetrievePipePolicy</b> supplies for <i>Value</i>. On output, this parameter contains the size that <b>RetrievePipePolicy</b> requires for <i>Value</i>.


### -param Value [out]

A pointer that receives the buffer that contains the WinUsb pipe policy.


## -returns
<b>RetrievePipePolicy</b> returns one of the following values: 
<dl>
<dt><b>S_OK </b></dt>
</dl>
<a href="wdf.iwdfusbtargetpipe_retrievepipepolicy">RetrievePipePolicy</a> successfully retrieved the WinUsb pipe policy. 
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
<a href="wdf.iwdfusbtargetpipe_retrievepipepolicy">RetrievePipePolicy</a> encountered an allocation failure.
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>This value corresponds to the error code that the WinUsb API returned.

 


## -remarks
Pipe policy controls the behavior of the USB pipe (for example, time-outs, handling short packets, and so on).

For more information about valid policy types that a UMDF driver can pass for the <i>PolicyType</i> parameter and values that the framework returns, see the <a href="buses.winusb_getpipepolicy">WinUsb_GetPipePolicy</a> function.

For information about the behavior of the pipe policies, see <a href="buses.winusb_functions_for_pipe_policy_modification">WinUSB Functions for Pipe Policy Modification</a>.

The <b>RetrievePipePolicy</b> method generates a UMDF request and synchronously sends the request to the I/O target.


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
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfusb.h (include Wudfusb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetpipe.md">IWDFUsbTargetPipe</a>
</dt>
<dt>
<a href="buses.winusb_getpipepolicy">WinUsb_GetPipePolicy</a>
</dt>
<dt>
<a href="wdf.iwdfusbtargetpipe_setpipepolicy">IWDFUsbTargetPipe::SetPipePolicy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetPipe::RetrievePipePolicy method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
