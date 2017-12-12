---
UID: NF.video.VideoPortQueryServices
title: VideoPortQueryServices function
author: windows-driver-content
description: The VideoPortQueryServices function exposes a specified interface that is implemented by the video port driver.
old-location: display\videoportqueryservices.htm
old-project: display
ms.assetid: 88d54fbc-e865-4a59-bb1c-75adfb49c355
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VideoPortQueryServices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortQueryServices
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# VideoPortQueryServices function



## -description
The <b>VideoPortQueryServices</b> function exposes a specified interface that is implemented by the video port driver.



## -syntax

````
VP_STATUS VideoPortQueryServices(
  _In_    PVOID               HwDeviceExtension,
  _In_    VIDEO_PORT_SERVICES ServicesType,
  _Inout_ PINTERFACE          Interface
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param ServicesType [in]

A value from the <a href="..\video\ne-video-video_port_services.md">VIDEO_PORT_SERVICES</a> enumerated type that specifies which interface is being requested.


### -param Interface [in, out]

Pointer to an <a href="kernel.interface">INTERFACE</a> structure, which contains basic information about the requested interface. See the following <b>Remarks</b> section for more information.


## -returns
If <b>VideoPortQueryServices</b> succeeds, it returns NO_ERROR; otherwise, it returns an error code.


## -remarks
If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesI2C</b>, the <i>Interface</i> parameter must be a pointer to a <a href="display.video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure.

Similarly, if the <i>ServicesType</i> parameter is set to <b>VideoPortServicesAGP</b>, the <i>Interface</i> parameter must be a pointer to either a <a href="display.video_port_agp_interface">VIDEO_PORT_AGP_INTERFACE</a> structure, or a <a href="display.video_port_agp_interface_2">VIDEO_PORT_AGP_INTERFACE_2</a> structure, each cast as a pointer to an <a href="kernel.interface">INTERFACE</a> structure. 

The VIDEO_PORT_AGP_INTERFACE and VIDEO_PORT_AGP_INTERFACE_2 structures are nearly identical, except that the latter structure has a member that points to the <a href="..\videoagp\nc-videoagp-pagp_set_rate.md">AgpSetRate</a> function, which is used to reset the transfer rate for an AGP chipset. A video miniport driver querying AGP support should call <b>VideoPortQueryServices</b> first with <i>Interface</i> pointing to a VIDEO_PORT_AGP_INTERFACE_2 structure. If that call fails, the miniport driver can then make another call to <b>VideoPortQueryServices</b>, this time with <i>Interface</i> pointing to a VIDEO_PORT_AGP_INTERFACE structure.

If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesInt10</b>, the <i>Interface</i> parameter must be a pointer to a <a href="display.video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure.

If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesDebugReport</b>, the <i>Interface</i> parameter must be a pointer to a <a href="display.video_port_debug_report_interface">VIDEO_PORT_DEBUG_REPORT_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure.

If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesWCMemoryProtection</b>, the <i>Interface</i> parameter must be a pointer to a <a href="display.video_port_wcmemoryprotection_interface">VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure. 


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
Version

</th>
<td width="70%">
Available in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
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
<a href="kernel.interface">INTERFACE</a>
</dt>
<dt>
<a href="display.video_port_agp_interface">VIDEO_PORT_AGP_INTERFACE</a>
</dt>
<dt>
<a href="display.video_port_agp_interface_2">VIDEO_PORT_AGP_INTERFACE_2</a>
</dt>
<dt>
<a href="display.video_port_i2c_interface">VIDEO_PORT_I2C_INTERFACE</a>
</dt>
<dt>
<a href="display.video_port_int10_interface">VIDEO_PORT_INT10_INTERFACE</a>
</dt>
<dt>
<a href="display.video_port_debug_report_interface">VIDEO_PORT_DEBUG_REPORT_INTERFACE</a>
</dt>
<dt>
<a href="display.video_port_wcmemoryprotection_interface">VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE</a>
</dt>
<dt>
<a href="..\videoagp\nc-videoagp-pagp_set_rate.md">AgpSetRate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortQueryServices function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
