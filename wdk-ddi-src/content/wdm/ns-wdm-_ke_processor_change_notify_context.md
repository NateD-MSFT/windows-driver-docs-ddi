---
UID: NS.WDM._KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT
title: _KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT
author: windows-driver-content
description: The KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure describes the notification context that is passed to a registered callback function when a new processor is dynamically added to a hardware partition.
old-location: kernel\ke_processor_change_notify_context.htm
old-project: kernel
ms.assetid: b8b8e2af-487c-4d7b-8af0-b6365d4703b0
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, *PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure



## -description
The <b>KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</b> structure describes the notification context that is passed to a registered callback function when a new processor is dynamically added to a hardware partition.



## -syntax

````
typedef struct _KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT {
  KE_PROCESSOR_CHANGE_NOTIFY_STATE State;
  ULONG                            NtNumber;
  NTSTATUS                         Status;
  PROCESSOR_NUMBER                 ProcNumber;
} KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT, *PKE_PROCESSOR_CHANGE_NOTIFY_CONTEXT;
````


## -struct-fields

### -field State

The state of the processor add operation. Possible values are as follows:




### -field KeProcessorAddStartNotify

The operating system is about to add the processor. At this state, a device driver that receives this notification can allocate any per-processor data structures and perform any other required tasks to prepare the driver for execution on the new processor.


### -field KeProcessorAddCompleteNotify

The operating system has successfully added the processor. At this state, a device driver that receives this notification can start scheduling threads on the new processor.


### -field KeProcessorAddFailureNotify

The operating system failed to add the processor. If a device driver receives this notification, it should free any per-processor data structures that it allocated for the new processor when it received the <b>KeProcessorAddStartNotify</b> notification.

</dd>
</dl>

### -field NtNumber

The processor index of the new processor. For information about the relationship between a processor index and a processor number, see <a href="kernel.kegetprocessornumberfromindex">KeGetProcessorNumberFromIndex</a>.


### -field Status

If the <b>State</b> member contains <b>KeProcessorAddFailureNotify</b>, this member contains the error status that indicates why the processor add operation failed.


### -field ProcNumber

The processor number of the new processor. This member is a <a href="kernel.processor_number">PROCESSOR_NUMBER</a> structure that specifies a group number and a group-relative processor number.


## -remarks
The <b>KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</b> structure is available starting with Windows Server 2008.

A device driver registers to receive notification when a new processor is dynamically added to the hardware partition by calling the <a href="kernel.keregisterprocessorchangecallback">KeRegisterProcessorChangeCallback</a> function. For more information about registering for this notification, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560897">Registering for Synchronous Driver Notification</a>.

When a new processor is dynamically added to the hardware partition, the operating system calls each registered callback function two times. The operating system calls each registered callback function the first time with the <b>KeProcessorAddStartNotify</b> state, and the second time with either the <b>KeProcessorAddCompleteNotify</b> state or the <b>KeProcessorAddFailureNotify</b> state.

A device driver's callback function that receives these notifications must not modify the contents of the <b>KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT</b> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows Server 2008.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.kegetprocessornumberfromindex">KeGetProcessorNumberFromIndex</a>
</dt>
<dt>
<a href="kernel.keregisterprocessorchangecallback">KeRegisterProcessorChangeCallback</a>
</dt>
<dt>
<a href="kernel.processor_number">PROCESSOR_NUMBER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KE_PROCESSOR_CHANGE_NOTIFY_CONTEXT structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
