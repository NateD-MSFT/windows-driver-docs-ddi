---
UID: NI.hidport.IOCTL_HID_READ_REPORT
title: IOCTL_HID_READ_REPORT
author: windows-driver-content
description: The IOCTL_HID_READ_REPORT request transfers an input report from a HIDClass device into the HID class driver's buffer.
old-location: hid\ioctl_hid_read_report.htm
old-project: hid
ms.assetid: 83a7cf49-6879-4e91-b398-d97d4b69e5b1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: HidRegisterMinidriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: Hidport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_READ_REPORT
req.alt-loc: hidport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# IOCTL_HID_READ_REPORT IOCTL



## -description
The IOCTL_HID_READ_REPORT request transfers an input report from a HIDClass device into the HID class driver's buffer.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -ioctlparameters

### -input-buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> contains the size of the buffer provided at <b>Irp-&gt;UserBuffer</b>.


### -input-buffer-length
The size of <b>OutputBufferLength</b>


### -output-buffer

       HID minidriver fills the system-resident buffer pointed to by <b>Irp-&gt;UserBuffer</b> with the report data retrieved from the device.


### -output-buffer-length
The size of the <b>UserBuffer</b>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:

<b>Information</b> is set to the number of bytes transferred from the device.

<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

HID minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is correct and not change the contents of the <b>Status</b> field.


## -remarks
IOCTL_HID_READ_REPORT  is typically used for continuously completing input reports that are sent by the device. This IOCTL is sent down by the HID class driver (HIDCLASS) in ping-pong fashion. In other words, as soon as a request is fulfilled (completed), another one can be sent down to the device, allowing for continuous reporting of data. This is an “asynchronous” mechanism, so for example, the device can use it to send  data up to the host, regarding  changes in state as those changes occur.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidport.h (include Hidport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="hid.hidd_getfeature">HidD_GetFeature</a>
</dt>
<dt>
<a href="hid.hidd_getinputreport">HidD_GetInputReport</a>
</dt>
<dt>
<a href="hid.hidd_setfeature">HidD_SetFeature</a>
</dt>
<dt>
<a href="hid.hidd_setoutputreport">HidD_SetOutputReport</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_feature.md">IOCTL_HID_GET_FEATURE</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_set_output_report.md">IOCTL_HID_SET_OUTPUT_REPORT</a>
</dt>
<dt>
<a href="..\hidport\ni-hidport-ioctl_hid_write_report.md">IOCTL_HID_WRITE_REPORT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_READ_REPORT control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
