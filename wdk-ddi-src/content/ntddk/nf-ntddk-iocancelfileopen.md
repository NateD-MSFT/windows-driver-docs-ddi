---
UID: NF.ntddk.IoCancelFileOpen
title: IoCancelFileOpen function
author: windows-driver-content
description: The IoCancelFileOpen routine can be used by a file system filter driver to close a file that has been opened by a file system driver in the filter driver's device stack.
old-location: ifsk\iocancelfileopen.htm
old-project: ifsk
ms.assetid: 249a77b4-c0da-4445-a669-1c4e2ced5b57
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IoCancelFileOpen
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCancelFileOpen
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
req.irql: PASSIVE_LEVEL
---

# IoCancelFileOpen function



## -description
The <b>IoCancelFileOpen</b> routine can be used by a file system filter driver to close a file that has been opened by a file system driver in the filter driver's device stack.



## -syntax

````
VOID IoCancelFileOpen(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PFILE_OBJECT   FileObject
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the top of the device stack immediately below the filter driver's device object.


### -param FileObject [in]

Pointer to the file object for the file to be closed.


## -returns
None


## -remarks
If a file system filter driver determines that a file-open or file-create request must fail after the lower-level drivers have already completed the request with STATUS_SUCCESS, it can use <b>IoCancelFileOpen</b> to close the file opened by the lower-level drivers.

A successful call to <b>IoCancelFileOpen</b> has the following effect: To minifilters and legacy filters that are above the caller in the file system stack, the create request appears to have failed. To those that are below the caller, the file appears to have been opened (or created) and then closed. 

Note that <b>IoCancelFileOpen</b> does not undo any modifications to the file. For example, <b>IoCancelFileOpen</b> does not delete a newly created file or restore a file that was overwritten or superseded to its previous state. 

A typical example is as follows:

A filter driver exists between a higher-level filter driver and a lower-level file system driver.

The filter driver passes an IRP_MJ_CREATE request down the device stack to the file system driver, and the file system driver completes the IRP_MJ_CREATE request with status STATUS_SUCCESS.

Before the filter driver completes the create request, it determines that the file must be closed.

The filter driver uses <b>IoCancelFileOpen</b> to close the file that was opened by the file system driver. 

After calling <b>IoCancelFileOpen</b>, the filter driver should complete the create request with an appropriate error code such as STATUS_UNSUCCESSFUL or STATUS_ACCESS_DENIED. In addition, it should set the <b>Irp-&gt;IoStatus.Information</b> field to zero. 

<b>IoCancelFileOpen</b> must be called before any handles are created for the file. Callers can check the <b>Flags</b> member of the <a href="kernel.file_object">FILE_OBJECT</a> structure that the <i>FileObject</i> parameter points to. If the FO_HANDLE_CREATED flag is set, this means that one or more handles have been created for the file, so it is not safe to call <b>IoCancelFileOpen</b>. 

<b>IoCancelFileOpen</b> sets the FO_FILE_OPEN_CANCELLED flag in the <b>Flags</b> member of the file object that <i>FileObject</i> points to. This flag indicates that the IRP_MJ_CREATE request has been canceled, and an IRP_MJ_CLOSE request will be issued for this file object. Once the create operation has been canceled, it cannot be reissued - that is, STATUS_REPARSE cannot be returned by the legacy filter driver if it has called the <b>IoCreateFileOpen</b> routine.

Minifilters should use <a href="ifsk.fltcancelfileopen">FltCancelFileOpen</a> instead of <b>IoCancelFileOpen</b>. 


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
This routine is available on Microsoft Windows 2000 and later. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltcancelfileopen">FltCancelFileOpen</a>
</dt>
<dt>
<a href="ifsk.fltreissuesynchronousio">FltReissueSynchronousIo</a>
</dt>
<dt>
<a href="kernel.iocreatefile">IoCreateFile</a>
</dt>
<dt>
<a href="ifsk.iocreatefileex">IoCreateFileEx</a>
</dt>
<dt>
<a href="ifsk.iocreatefilespecifydeviceobjecthint">IoCreateFileSpecifyDeviceObjectHint</a>
</dt>
<dt>
<a href="ifsk.irp_mj_close">IRP_MJ_CLOSE</a>
</dt>
<dt>
<a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="kernel.zwcreatefile">ZwCreateFile</a>
</dt>
<dt>
<a href="kernel.zwopenfile">ZwOpenFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoCancelFileOpen routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
