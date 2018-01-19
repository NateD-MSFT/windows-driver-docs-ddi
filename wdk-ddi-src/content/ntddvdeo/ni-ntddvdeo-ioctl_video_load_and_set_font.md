---
UID : NI:ntddvdeo.IOCTL_VIDEO_LOAD_AND_SET_FONT
title : IOCTL_VIDEO_LOAD_AND_SET_FONT
author : windows-driver-content
description : Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location : display\ioctl_video_load_and_set_font.htm
old-project : display
ms.assetid : 13771df5-f66c-4dd9-b2d3-4477fda82f8f
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddvdeo.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_VIDEO_LOAD_AND_SET_FONT
req.alt-loc : Ntddvdeo.h
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
req.typenames : "*PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS"
---

# IOCTL_VIDEO_LOAD_AND_SET_FONT IOCTL
Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.



Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The VRP <b>InputBuffer</b> contains a VIDEO_LOAD_FONT_INFORMATION structure describing the font's width, height, and size, as well as a pointer to the font buffer.

### Input Buffer Length
<text></text>

### Output Buffer
None

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddvdeo.h |
| **IRQL** |  |