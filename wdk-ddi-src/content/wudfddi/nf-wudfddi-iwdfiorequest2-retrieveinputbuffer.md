---
UID: NF.wudfddi.IWDFIoRequest2.RetrieveInputBuffer
title: IWDFIoRequest2::RetrieveInputBuffer method
author: windows-driver-content
description: The RequestRetrieveInputBuffer method retrieves an I/O request's input buffer.
old-location: wdf\iwdfiorequest2_retrieveinputbuffer.htm
old-project: wdf
ms.assetid: f727d9b7-d7ea-4551-bc5a-7829f9807e02
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFIoRequest2, IWDFIoRequest2::RetrieveInputBuffer, RetrieveInputBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFIoRequest2.RetrieveInputBuffer
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

# IWDFIoRequest2::RetrieveInputBuffer method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="wdf.wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> method retrieves an I/O request's input buffer.



## -syntax

````
HRESULT RetrieveInputBuffer(
  [in]            SIZE_T MinimumRequiredCb,
  [out]           PVOID  *Buffer,
  [out, optional] SIZE_T *BufferCb
);
````


## -parameters

### -param MinimumRequiredCb [in]

The minimum buffer size, in bytes, that the driver needs to process the I/O request. This value can be zero if there is no minimum buffer size.


### -param Buffer [out]

A pointer to a location that receives the buffer's address.


### -param BufferCb [out, optional]

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## -returns

<a href="wdf.wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</b></dt>
</dl>The I/O request did not provide an input buffer, or the size of the input buffer is less than the minimum size that <i>MinimumRequiredCb</i> specifies.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>Not enough memory is available to retrieve the buffer. The driver should complete the request with an error status value.

 

This method might return one of the other values that Winerror.h contains.






## -remarks
A request's input buffer contains information, such as data to be written to a disk, that the originator of the request supplied. Your driver can call <a href="wdf.wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> to obtain the input buffer for a write request or a device I/O control request, but not for a read request (because read requests do not provide input data).

The <a href="wdf.wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> method retrieves the input buffer for I/O requests that use the <a href="wdf.accessing_data_buffers_in_umdf_drivers#using_buffered_i_o_in_umdf_drivers#using_buffered_i_o_in_umdf_drivers">buffered I/O</a> or <a href="wdf.accessing_data_buffers_in_umdf_drivers#using_direct_i_o_in_umdf_drivers#using_direct_i_o_in_umdf_drivers">direct I/O</a> method for accessing data buffers.

If <a href="wdf.wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a> returns S_OK, the driver receives the address and, optionally, the size of the input buffer. 

The driver can access the retrieved buffer until it <a href="wdf.completing_i_o_requests">completes</a> the I/O request.

Instead of calling <a href="wdf.wdfrequestretrieveinputbuffer">RequestRetrieveInputBuffer</a>, the driver can call <a href="wdf.iwdfiorequest2_retrieveinputmemory">IWDFIoRequest2::RetrieveInputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about accessing an I/O request's data buffers, see <a href="wdf.accessing_data_buffers_in_umdf_drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.

The following code example shows a segment of a serial port driver's <a href="wdf.iqueuecallbackdeviceiocontrol_ondeviceiocontrol">IQueueCallbackDeviceIoControl::OnDeviceIoControl</a> callback function. From an I/O request's input buffer, the code segment obtains the baud rate that should be set for the device.


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
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
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
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_getinputmemory">IWDFIoRequest::GetInputMemory</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_getoutputmemory">IWDFIoRequest::GetOutputMemory</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest2_retrieveinputmemory">IWDFIoRequest2::RetrieveInputMemory</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest2_retrieveoutputbuffer">IWDFIoRequest2::RetrieveOutputBuffer</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest2_retrieveoutputmemory">IWDFIoRequest2::RetrieveOutputMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::RetrieveInputBuffer method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
