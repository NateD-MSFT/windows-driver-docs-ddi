---
UID: NE.wdfusb._WDF_USB_BMREQUEST_DIRECTION
title: _WDF_USB_BMREQUEST_DIRECTION
author: windows-driver-content
description: The WDF_USB_BMREQUEST_DIRECTION enumeration identifies the data transfer direction for a USB control transfer.
old-location: wdf\wdf_usb_bmrequest_direction.htm
old-project: wdf
ms.assetid: e39748b8-d84c-4f9e-a790-bff192a6769c
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_USB_BMREQUEST_DIRECTION, WDF_USB_BMREQUEST_DIRECTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_BMREQUEST_DIRECTION
req.alt-loc: wdfusb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL  (See Remarks section.)
req.product: Windows 10 or later.
---

# _WDF_USB_BMREQUEST_DIRECTION enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration identifies the data transfer direction for a USB control transfer. 



## -syntax

````
typedef enum _WDF_USB_BMREQUEST_DIRECTION { 
  BmRequestHostToDevice  = BMREQUEST_HOST_TO_DEVICE,
  BmRequestDeviceToHost  = BMREQUEST_DEVICE_TO_HOST
} WDF_USB_BMREQUEST_DIRECTION;
````


## -enum-fields

### -field BmRequestHostToDevice

The data transfer direction is from the host system to the device.


### -field BmRequestDeviceToHost

The data transfer direction is from the device to the host system.


## -remarks
The <b>WDF_USB_BMREQUEST_DIRECTION</b> enumeration is used in the <a href="wdf.wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

For more information about the data transfer direction for a USB control transfer, see the USB specification.


## -requirements
<table>
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
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_usb_control_setup_packet">WDF_USB_CONTROL_SETUP_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_BMREQUEST_DIRECTION enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
