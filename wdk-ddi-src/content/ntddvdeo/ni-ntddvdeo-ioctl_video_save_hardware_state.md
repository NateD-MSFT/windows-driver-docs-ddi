---
UID: NI.ntddvdeo.IOCTL_VIDEO_SAVE_HARDWARE_STATE
title: IOCTL_VIDEO_SAVE_HARDWARE_STATE
author: windows-driver-content
description: Saves the state of the video adapter in the VRP OutputBuffer. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.
old-location: display\ioctl_video_save_hardware_state.htm
old-project: display
ms.assetid: 24d786df-2cdd-465c-b468-212e109d5ae1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VIDEO_SAVE_HARDWARE_STATE
req.alt-loc: Ntddvdeo.h
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

# IOCTL_VIDEO_SAVE_HARDWARE_STATE IOCTL



## -description

Saves the state of the video adapter in the VRP <b>OutputBuffer</b>. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.



Saves the state of the video adapter in the VRP <b>OutputBuffer</b>. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.



## -ioctlparameters

### -input-buffer
None


### -input-buffer-length

<text></text>

### -output-buffer
The miniport driver returns a VIDEO_HARDWARE_STATE structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the miniport driver successfully saves the adapter state, it sets the <b>Information</b> member of the <a href="display.status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_HARDWARE_STATE); otherwise, the miniport driver sets this member to zero.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.status_block">STATUS_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_SAVE_HARDWARE_STATE control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
