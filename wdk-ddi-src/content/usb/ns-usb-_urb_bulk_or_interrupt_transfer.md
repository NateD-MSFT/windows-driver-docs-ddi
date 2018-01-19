---
UID : NS:usb._URB_BULK_OR_INTERRUPT_TRANSFER
title : _URB_BULK_OR_INTERRUPT_TRANSFER
author : windows-driver-content
description : The _URB_BULK_OR_INTERRUPT_TRANSFER structure is used by USB client drivers to send or receive data on a bulk pipe or on an interrupt pipe.
old-location : buses\_urb_bulk_or_interrupt_transfer.htm
old-project : usbref
ms.assetid : 398f50ad-4c58-4585-8fb8-c523b74793e9
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _URB_BULK_OR_INTERRUPT_TRANSFER,
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : usb.h
req.include-header : Usb.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : _URB_BULK_OR_INTERRUPT_TRANSFER
req.alt-loc : usb.h
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
req.typenames : 
req.product : Windows 10 or later.
---

# _URB_BULK_OR_INTERRUPT_TRANSFER structure
The <b>_URB_BULK_OR_INTERRUPT_TRANSFER</b> structure is used by USB client drivers to send or receive data on a bulk pipe or on an interrupt pipe.

## Syntax
````
struct _URB_BULK_OR_INTERRUPT_TRANSFER {
  struct URB_HEADER  Hdr;
  USBD_PIPE_HANDLE    PipeHandle;
  ULONG               TransferFlags;
  ULONG               TransferBufferLength;
  PVOID               TransferBuffer;
  PMDL                TransferBufferMDL;
  struct URB  *UrbLink;
  struct URB_HCD_AREA  hca;
};
````

## Members

        
            `hca`

            Reserved. Do not use.
        
            `Hdr`

            Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_BULK_OR_INTERRUPT_TRANSFER, and <b>Hdr.Length</b> must be set to <code>sizeof(_URB_BULK_OR_INTERRUPT_TRANSFER)</code>.
        
            `PipeHandle`

            Specifies an opaque handle to the bulk or interrupt pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.
        
            `TransferBuffer`

            Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>. The contents of this buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified this buffer will contain data read from the device on return from the host controller driver. Otherwise, this buffer contains driver-supplied data for transfer to the device.
        
            `TransferBufferLength`

            Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.
        
            `TransferBufferMDL`

            Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. The contents of the buffer depend on the value of <b>TransferFlags</b>. If USBD_TRANSFER_DIRECTION_IN is specified, the described buffer will contain data read from the device on return from the host controller driver. Otherwise, the buffer contains driver-supplied data for transfer to the device. This MDL must be allocated from nonpaged pool.
        
            `TransferFlags`

            Specifies zero, one, or a combination of the following flags:



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
        
            `UrbLink`

            Reserved. Do not use.

    ## Remarks
        Drivers can use the <b>UsbBuildInterruptOrBulkTransferRequest</b> service routine to format this URB. Buffers specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL </b>must be nonpageable. 

In an <a href="..\usb\ns-usb-_urb.md">URB</a>, both <b>TransferBuffer</b> and <b>TransferBufferMDL</b> parameters can be non-NULL values, at the same time. In that case, the transfer buffer and the MDL pointed to <b>TransferBuffer</b> and <b>TransferBufferMDL</b> must point to the same  buffer.

The USB bus driver processes this URB at DISPATCH_LEVEL.

The reserved members of this structure must be treated as opaque and are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usb.h (include Usb.h) |

    ## See Also

        <dl>
<dt>
<a href="..\usb\ns-usb-_urb.md">URB</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_BULK_OR_INTERRUPT_TRANSFER structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>