---
UID: NF.wudfddi.IWDFInterrupt.Enable
title: IWDFInterrupt::Enable method
author: windows-driver-content
description: The Enable method enables a specified device interrupt by calling the driver's OnInterruptEnable callback function.
old-location: wdf\iwdfinterrupt_enable.htm
old-project: wdf
ms.assetid: 605C58C2-9A4F-4185-BB5C-95C9F5180C05
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFInterrupt, IWDFInterrupt::Enable, Enable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFInterrupt.Enable
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

# IWDFInterrupt::Enable method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Enable</b> method enables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_enable.md">OnInterruptEnable</a> callback function.



## -syntax

````
void Enable();
````


## -parameters


## -returns
This method does not return a value.

This method does not return a value.

This method does not return a value.


## -remarks
Most UMDF drivers do not need to call <b>IWDFInterrupt::Enable</b>, because the framework calls the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_enable.md">OnInterruptEnable</a> callback function each time the device enters its working (D0) state.



For more information about handling interrupts in UMDF drivers, see <a href="wdf.accessing_hardware_and_handling_interrupts">Accessing Hardware and Handling Interrupts</a>.

The following code example enables the device interrupt that is associated with a specified interrupt object.


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
1.11

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h</dt>
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
<a href="..\wudfddi\nn-wudfddi-iwdfinterrupt.md">IWDFInterrupt</a>
</dt>
<dt>
<a href="wdf.iwdfinterrupt_disable">IWDFInterrupt::Disable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt::Enable method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
