---
UID: NF.storport.StorPortInitializeTimer
title: StorPortInitializeTimer function
author: windows-driver-content
description: Creates a Storport timer context object.
old-location: storage\storportinitializetimer.htm
old-project: storage
ms.assetid: 1F43EEDC-5DB4-4ABE-BBC6-A4A51FCAF0B6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: StorPortInitializeTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortInitializeTimer
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# StorPortInitializeTimer function



## -description
Creates a Storport timer context object.



## -syntax

````
ULONG StorPortInitializeTimer(
  _In_  PVOID HwDeviceExtension,
  _Out_ PVOID *TimerHandle
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param TimerHandle [out]

A pointer to an opaque buffer that holds context information for the timer.


## -returns
The <b>StorPortInitializeTimer</b> routine returns one of these status codes:
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>Current IRQL &gt; DISPATCH_LEVEL.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>Either <i>HwDeviceExtension</i> or <i>TimerHandle</i> is NULL.
<dl>
<dt><b>STOR_STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl> Insufficient resources are available to initialize the timer context.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The timer context was successfully initialized.
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>The number of supported timers is exceeded.

 


## -remarks
Storport provides a single timer to a miniport driver by using the  <b>RequestTimerCall</b> notification type in <a href="storage.storportnotification">StorPortNotification</a>. If a miniport requires more than one timer, additional timers are created with <b>StorPortInitializeTimer</b>.

It is recommended that miniports call <b>StorPortInitializeTimer</b> in the <a href="storage.hwstorfindadapter">HwStorFindAdapter</a> function to ensure that the additional timer resources are available.

Miniports can use this routine to set coalescing timers to create a delay period after an initial timeout.

Prior to Windows 8, a maximum of 4 timers can be created with <b>StorPortInitializeTimer</b>.
Starting with Windows 8, there is no maximum timers limitation.


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
Available in Windows 8 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
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
<a href="storage.hwstorfindadapter">HwStorFindAdapter</a>
</dt>
<dt>
<a href="storage.storportfreetimer">StorPortFreeTimer</a>
</dt>
<dt>
<a href="storage.storportnotification">StorPortNotification</a>
</dt>
<dt>
<a href="storage.storportrequesttimer">StorPortRequestTimer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInitializeTimer routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
