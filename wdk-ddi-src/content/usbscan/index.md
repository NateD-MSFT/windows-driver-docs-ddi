---
UID : NA:usbscan
ms.assetid : 31ca997d-12f9-393e-bfce-cdcf84179963
ms.author : windowsdriverdev
ms.date : 01/18/18
ms.keywords : 
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : portal
---

# usbscan.h header



usbscan.h contains the following programming interfaces:




## IOCTLs
| Title | Description |
| ---- |:---- |
| [IOCTL_CANCEL_IO](ni-usbscan-ioctl_cancel_io.md) | Cancels activity on the specified USB transfer pipe that is associated with the specified device handle. |
| [IOCTL_GET_CHANNEL_ALIGN_RQST](ni-usbscan-ioctl_get_channel_align_rqst.md) | Returns a USB device's maximum packet size for the read, write, and interrupt transfer pipes associated with the specified device handle. |
| [IOCTL_GET_DEVICE_DESCRIPTOR](ni-usbscan-ioctl_get_device_descriptor.md) | Returns vendor and device identifiers. |
| [IOCTL_GET_PIPE_CONFIGURATION](ni-usbscan-ioctl_get_pipe_configuration.md) | Returns a description of every transfer pipe supported for a device. |
| [IOCTL_GET_USB_DESCRIPTOR](ni-usbscan-ioctl_get_usb_descriptor.md) | Returns a specified USB Descriptor. |
| [IOCTL_GET_VERSION](ni-usbscan-ioctl_get_version.md) | Returns the version number of the driver. |
| [IOCTL_READ_REGISTERS](ni-usbscan-ioctl_read_registers.md) | Reads from USB device registers, using the control pipe. |
| [IOCTL_RESET_PIPE](ni-usbscan-ioctl_reset_pipe.md) | Resets the specified USB transfer pipe that is associated with the specified device handle. |
| [IOCTL_SEND_USB_REQUEST](ni-usbscan-ioctl_send_usb_request.md) | Sends a vendor-defined request to a USB device, using the control pipe, and optionally sends or receives additional data. |
| [IOCTL_SET_TIMEOUT](ni-usbscan-ioctl_set_timeout.md) | Sets the time-out value for USB bulk IN, bulk OUT, or interrupt pipe access. |
| [IOCTL_WAIT_ON_DEVICE_EVENT](ni-usbscan-ioctl_wait_on_device_event.md) | Returns information about an event occurring on a USB interrupt pipe. |
| [IOCTL_WRITE_REGISTERS](ni-usbscan-ioctl_write_registers.md) | Writes to USB device registers, using the control pipe. |




## Structures
| Title | Description |
| ---- |:---- |
| [_CHANNEL_INFO](ns-usbscan-_channel_info.md) | The CHANNEL_INFO structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_CHANNEL_ALIGN_RQST. |
| [_DEVICE_DESCRIPTOR](ns-usbscan-_device_descriptor.md) | The DEVICE_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_DEVICE_DESCRIPTOR. |
| [_DRV_VERSION](ns-usbscan-_drv_version.md) | The DRV_VERSION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_VERSION. |
| [_IO_BLOCK](ns-usbscan-_io_block.md) | The IO_BLOCK structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_READ_REGISTERS or IOCTL_WRITE_REGISTERS. |
| [_IO_BLOCK_EX](ns-usbscan-_io_block_ex.md) | The IO_BLOCK_EX structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_SEND_USB_REQUEST. |
| [_USBSCAN_GET_DESCRIPTOR](ns-usbscan-_usbscan_get_descriptor.md) | The USBSCAN_GET_DESCRIPTOR structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_USB_DESCRIPTOR. |
| [_USBSCAN_PIPE_CONFIGURATION](ns-usbscan-_usbscan_pipe_configuration.md) | The USBSCAN_PIPE_CONFIGURATION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_PIPE_CONFIGURATION. |
| [_USBSCAN_PIPE_INFORMATION](ns-usbscan-_usbscan_pipe_information.md) | The USBSCAN_PIPE_INFORMATION structure is used to describe a USB transfer pipe for a still image device. An array of USBSCAN_PIPE_INFORMATION structures is supplied within a USBSCAN_PIPE_CONFIGURATION structure. |
| [_USBSCAN_TIMEOUT](ns-usbscan-_usbscan_timeout.md) | The USBSCAN_TIMEOUT structure stores time-out values for USB bulk IN and bulk OUT operations, and interrupts. |


## Enumerations
| Title | Description |
| ---- |:---- |
| [_RAW_PIPE_TYPE](ne-usbscan-_raw_pipe_type.md) | The RAW_PIPE_TYPE data type is used to specify the type of a USB pipe. |
| [PIPE_TYPE](ne-usbscan-pipe_type.md) | The PIPE_TYPE data type is used as input to the DeviceIoControl function, if the I/O control code is IOCTL_CANCEL_IO or IOCTL_RESET_PIPE. |