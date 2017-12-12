---
UID: NC.wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE
author: windows-driver-content
description: A driver's EvtChildListIdentificationDescriptionDuplicate event callback function duplicates a child identification description.
old-location: wdf\evtchildlistidentificationdescriptionduplicate.htm
old-project: wdf
ms.assetid: 5c2ec27c-2d88-4e0c-8f11-4f58d720df46
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: EvtChildListIdentificationDescriptionDuplicate
req.alt-loc: WdfChildlist.h
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

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE callback



## -description
<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtChildListIdentificationDescriptionDuplicate</i> event callback function duplicates a child identification description.



## -prototype

````
EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE EvtChildListIdentificationDescriptionDuplicate;

NTSTATUS EvtChildListIdentificationDescriptionDuplicate(
  _In_  WDFCHILDLIST                                 ChildList,
  _In_  PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER SourceIdentificationDescription,
  _Out_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER DestinationIdentificationDescription
)
{ ... }
````


## -parameters

### -param ChildList [in]

A handle to a framework child-list object.


### -param SourceIdentificationDescription [in]

A pointer to a <a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the source location of the child identification description.


### -param DestinationIdentificationDescription [out]

A pointer to a WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure that identifies the destination location of the duplicate child identification description.


## -returns
The <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if the operation succeeds. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 


## -remarks
If a bus driver is using <a href="wdf.dynamic_enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function by calling <a href="wdf.wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="wdf.wdfchildlistcreate">WdfChildListCreate</a>.

The framework duplicates driver-supplied identification descriptions so that it can have internal copies of the descriptions.

The <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function must create a duplicate copy of an identification description. A driver must supply this callback function if the framework cannot call <a href="kernel.rtlcopymemory">RtlCopyMemory</a> to duplicate the identification description. (The framework cannot call <b>RtlCopyMemory</b> if the description contains pointers to additional memory.)

If your driver does not provide an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function, the framework duplicates identification descriptions by calling <a href="kernel.rtlcopymemory">RtlCopyMemory</a>.

The following steps describe a typical scenario:

The driver determines that a child device exists.

The driver creates an identification description by filling in a driver-defined structure that contains a <a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure and possibly by dynamically allocating addition memory to store identification information that has a device-specific size. 

The driver calls <a href="wdf.wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> to report a child device, supplying a pointer to the identification description. 

The framework calls the <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function (if it exists) or <a href="kernel.rtlcopymemory">RtlCopyMemory</a> to duplicate the identification description so that it can have an internal copy of the description.

The framework can use <a href="kernel.rtlcopymemory">RtlCopyMemory</a> to duplicate an identification description, if the description consists of a single structure with a predetermined size that is specified by the <b>IdentificationDescriptionSize</b> member of the WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function. The callback function must do the following:

Allocate additional memory, typically by calling <a href="kernel.exallocatepool">ExAllocatePool</a>.

Store the allocated memory's address in the driver-defined address description structure (that is, the callback function's <i>DestinationIdentificationDescription</i> structure).

Copy other structure members from the callback function's <i>SourceIdentificationDescription</i> structure to the callback function's <i>DestinationIdentificationDescription</i> structure.

The only <a href="wdf.wdf_child-list_object_reference">framework child-list object method</a> that a driver's <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function can call is <a href="wdf.wdfchildlistgetdevice">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function. This callback function must only perform operations that are related to the uplication operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

If your driver supplies an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function, it might also need <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_copy.md">EvtChildListIdentificationDescriptionCopy</a>, <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>, and <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup.md">EvtChildListIdentificationDescriptionCleanup</a> callback functions.

For more information about dynamic enumeration, see <a href="wdf.enumerating_the_devices_on_a_bus">Enumerating the Devices on a Bus</a>.

To define an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function that is named <i>MyChildListIdentificationDescriptionDuplicate</i>, use the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE</b> type as shown in this code example:

To define an <i>EvtChildListIdentificationDescriptionDuplicate</i> callback function that is named <b>MyChildListIdentificationDescriptionDuplicate</b>, you must first provide a function declaration that SDV and other verification tools require, as follows:

Then, implement your callback function as follows:

The <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>WdfChildlist.h (include Wdf.h)</dt>
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
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup.md">EvtChildListIdentificationDescriptionCleanup</a>
</dt>
<dt>
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>
</dt>
<dt>
<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_copy.md">EvtChildListIdentificationDescriptionCopy</a>
</dt>
<dt>
<a href="kernel.exallocatepool">ExAllocatePool</a>
</dt>
<dt>
<a href="kernel.rtlcopymemory">RtlCopyMemory</a>
</dt>
<dt>
<a href="wdf.wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>
</dt>
<dt>
<a href="wdf.wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>
</dt>
<dt>
<a href="wdf.wdfchildlistcreate">WdfChildListCreate</a>
</dt>
<dt>
<a href="wdf.wdfchildlistgetdevice">WdfChildListGetDevice</a>
</dt>
<dt>
<a href="wdf.wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE callback function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
