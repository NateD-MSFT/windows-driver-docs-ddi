---
UID: NN.wudfddi.IWDFInterrupt~r1
title: IWDFInterrupt
author: windows-driver-content
description: This interface exposes an interrupt object.
old-location: wdf\iwdfinterrupt.htm
old-project: wdf
ms.assetid: 729A2361-6FE1-4096-AC8B-3D042326EE5C
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: __MIDL___MIDL_itf_wudfddi_0000_0000_0001, POWER_ACTION, *PPOWER_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFInterrupt
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
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# IWDFInterrupt interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

This interface exposes an interrupt object.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFInterrupt</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>. <b>IWDFInterrupt</b> also has these types of members:

The <b>IWDFInterrupt</b> interface has these methods.

The <a href="wdf.iwdfinterrupt_acquireinterruptlock">AcquireInterruptLock</a> method begins a code sequence that executes while holding an interrupt object's lock.

The <a href="wdf.iwdfinterrupt_disable">Disable</a> method disables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_disable.md">OnInterruptDisable</a> callback function.

The <a href="wdf.iwdfinterrupt_enable">Enable</a> method enables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_enable.md">OnInterruptEnable</a> callback function.

The <a href="wdf.iwdfinterrupt_getdevice">GetDevice</a> method returns the framework device object interface for this interrupt object.

The <a href="wdf.iwdfinterrupt_getinfo">GetInfo</a> method retrieves information about a specified interrupt.

The <a href="wdf.iwdfinterrupt_queueworkitemforisr">QueueWorkItemForIsr</a> method queues a work item to process interrupt-related work outside of the interrupt service routine.

The <a href="wdf.iwdfinterrupt_releaseinterruptlock">ReleaseInterruptLock</a> method ends a code sequence that executes while holding an interrupt object's lock.

The <a href="wdf.iwdfinterrupt_setextendedpolicy">SetExtendedPolicy</a> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
  

The <a href="wdf.iwdfinterrupt_setpolicy">SetPolicy</a> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.

The <a href="wdf.iwdfinterrupt_trytoacquireinterruptlock">TryToAcquireInterruptLock</a> method acquires the interrupt lock if no other thread has already acquired it.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFInterrupt</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>. <b>IWDFInterrupt</b> also has these types of members:

The <b>IWDFInterrupt</b> interface has these methods.

The <a href="wdf.iwdfinterrupt_acquireinterruptlock">AcquireInterruptLock</a> method begins a code sequence that executes while holding an interrupt object's lock.

The <a href="wdf.iwdfinterrupt_disable">Disable</a> method disables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_disable.md">OnInterruptDisable</a> callback function.

The <a href="wdf.iwdfinterrupt_enable">Enable</a> method enables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_enable.md">OnInterruptEnable</a> callback function.

The <a href="wdf.iwdfinterrupt_getdevice">GetDevice</a> method returns the framework device object interface for this interrupt object.

The <a href="wdf.iwdfinterrupt_getinfo">GetInfo</a> method retrieves information about a specified interrupt.

The <a href="wdf.iwdfinterrupt_queueworkitemforisr">QueueWorkItemForIsr</a> method queues a work item to process interrupt-related work outside of the interrupt service routine.

The <a href="wdf.iwdfinterrupt_releaseinterruptlock">ReleaseInterruptLock</a> method ends a code sequence that executes while holding an interrupt object's lock.

The <a href="wdf.iwdfinterrupt_setextendedpolicy">SetExtendedPolicy</a> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
  

The <a href="wdf.iwdfinterrupt_setpolicy">SetPolicy</a> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.

The <a href="wdf.iwdfinterrupt_trytoacquireinterruptlock">TryToAcquireInterruptLock</a> method acquires the interrupt lock if no other thread has already acquired it.

 


## -members
The <b>IWDFInterrupt</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_acquireinterruptlock">AcquireInterruptLock</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_acquireinterruptlock">AcquireInterruptLock</a> method begins a code sequence that executes while holding an interrupt object's lock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_disable">Disable</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_disable">Disable</a> method disables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_disable.md">OnInterruptDisable</a> callback function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_enable">Enable</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_enable">Enable</a> method enables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_enable.md">OnInterruptEnable</a> callback function.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_getdevice">GetDevice</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_getdevice">GetDevice</a> method returns the framework device object interface for this interrupt object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_getinfo">GetInfo</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_getinfo">GetInfo</a> method retrieves information about a specified interrupt.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_queueworkitemforisr">QueueWorkItemForIsr</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_queueworkitemforisr">QueueWorkItemForIsr</a> method queues a work item to process interrupt-related work outside of the interrupt service routine.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_releaseinterruptlock">ReleaseInterruptLock</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_releaseinterruptlock">ReleaseInterruptLock</a> method ends a code sequence that executes while holding an interrupt object's lock.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_setextendedpolicy">SetExtendedPolicy</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_setextendedpolicy">SetExtendedPolicy</a> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
  

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_setpolicy">SetPolicy</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_setpolicy">SetPolicy</a> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfinterrupt_trytoacquireinterruptlock">TryToAcquireInterruptLock</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfinterrupt_trytoacquireinterruptlock">TryToAcquireInterruptLock</a> method acquires the interrupt lock if no other thread has already acquired it.

</td>
</tr>
</table>The <a href="wdf.iwdfinterrupt_acquireinterruptlock">AcquireInterruptLock</a> method begins a code sequence that executes while holding an interrupt object's lock.

The <a href="wdf.iwdfinterrupt_disable">Disable</a> method disables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_disable.md">OnInterruptDisable</a> callback function.

The <a href="wdf.iwdfinterrupt_enable">Enable</a> method enables a specified device interrupt by calling the driver's <a href="..\wudfinterrupt\nc-wudfinterrupt-wudf_interrupt_enable.md">OnInterruptEnable</a> callback function.

The <a href="wdf.iwdfinterrupt_getdevice">GetDevice</a> method returns the framework device object interface for this interrupt object.

The <a href="wdf.iwdfinterrupt_getinfo">GetInfo</a> method retrieves information about a specified interrupt.

The <a href="wdf.iwdfinterrupt_queueworkitemforisr">QueueWorkItemForIsr</a> method queues a work item to process interrupt-related work outside of the interrupt service routine.

The <a href="wdf.iwdfinterrupt_releaseinterruptlock">ReleaseInterruptLock</a> method ends a code sequence that executes while holding an interrupt object's lock.

The <a href="wdf.iwdfinterrupt_setextendedpolicy">SetExtendedPolicy</a> method specifies the interrupt priority, processor affinity, affinity policy, and processor group for a specified interrupt.
  

The <a href="wdf.iwdfinterrupt_setpolicy">SetPolicy</a> method specifies the interrupt priority, processor affinity, and affinity policy for a specified interrupt.

The <a href="wdf.iwdfinterrupt_trytoacquireinterruptlock">TryToAcquireInterruptLock</a> method acquires the interrupt lock if no other thread has already acquired it.

 


## -remarks


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
<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFInterrupt interface%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
