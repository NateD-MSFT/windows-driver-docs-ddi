---
UID : NI:usbioctl.IOCTL_USB_DIAGNOSTIC_MODE_ON
title : IOCTL_USB_DIAGNOSTIC_MODE_ON
author : windows-driver-content
description : The IOCTL_USB_DIAGNOSTIC_MODE_ON I/O control has been deprecated. Do not use.
old-location : buses\ioctl_usb_diagnostic_mode_on.htm
old-project : usbref
ms.assetid : 9b3b7d11-a91c-4905-b639-d9843f05d65e
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : usbioctl.h
req.include-header : Usbioctl.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_USB_DIAGNOSTIC_MODE_ON
req.alt-loc : Usbioctl.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : USB_HUB_TYPE
req.product : Windows 10 or later.
---

# IOCTL_USB_DIAGNOSTIC_MODE_ON IOCTL
The <b>IOCTL_USB_DIAGNOSTIC_MODE_ON</b> I/O control has been deprecated. Do not use.



The <b>IOCTL_USB_DIAGNOSTIC_MODE_ON</b> I/O control has been deprecated. Do not use.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | usbioctl.h (include Usbioctl.h) |
| **IRQL** |  |