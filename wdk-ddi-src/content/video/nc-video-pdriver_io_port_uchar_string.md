---
UID: NC:video.PDRIVER_IO_PORT_UCHAR_STRING
title: PDRIVER_IO_PORT_UCHAR_STRING
author: windows-driver-content
description: SvgaHwIoPortUcharString traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of UCHAR-sized data.
old-location: display\svgahwioportucharstring.htm
old-project: display
ms.assetid: 7158cd6c-a662-46e8-bb7c-ea852797c39e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PDRIVER_IO_PORT_UCHAR_STRING, SvgaHwIoPortUcharString, SvgaHwIoPortUcharString callback function [Display Devices], VideoMiniport_Functions_4008d0c6-1185-46fd-acb1-60a8ddd3b45b.xml, display.svgahwioportucharstring, video/SvgaHwIoPortUcharString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	SvgaHwIoPortUcharString
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PDRIVER_IO_PORT_UCHAR_STRING callback


## -description


<i>SvgaHwIoPortUcharString</i> traps an I/O port to which a full-screen MS-DOS application in an x86-based machine is sending a sequence of UCHAR-sized data.


## -parameters




### -param Context

Specifies the miniport driver-determined context value that was set in the <b>EmulatorAccessEntriesContext</b> member of VIDEO_PORT_CONFIG_INFO.


### -param Port

Specifies the mapped I/O port.


### -param AccessMode

Specifies the type of access allowed, which can be one or a combination (ORed) of the following values:


<dl>
<dt>EMULATOR_READ_ACCESS</dt>
<dt>EMULATOR_WRITE_ACCESS</dt>
</dl>



### -param Data

Pointer to the UCHAR string to be transferred. One character at a time is hooked out until the whole string is transferred.


### -param DataLength

Specifies the number of UCHAR values in the string.


## -returns



<i>SvgaHwIoPortUcharString</i> returns the final status of the operation.




## -remarks



Only miniport drivers of VGA-compatible SVGA adapters have <i>SvgaHwIoPortXxx</i> functions. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>.)

<i>SvgaHwIoPortUcharString</i> intercepts any byte access attempted by a full-screen MS-DOS application issuing either or both of the instructions <b>REP OUTSB DX, ESI</b> and <b>REP INSB EDI, DX</b>.

If the miniport driver enables the <i>Port</i> for direct access by calling <b>VideoSetTrappedEmulatorPorts</b>, its <i>SvgaHwIoPortUcharString</i> function will not be called. Such an application then will have direct access to the I/O port, unless the miniport driver disables the port with another call to <b>VideoSetTrappedEmulatorPorts</b>.

If one or more application-issued x86 <b>INSB</b> or <b>OUTSB</b> instructions might affect the state of the VGA-compatible adapter sequencer register, miscellaneous output register, or any adapter-specific register and, thereby, cause the machine to hang, the miniport driver must <i>not</i> enable the port for direct access by calling <b>VideoPortSetTrappedEmulatorPorts</b>.

<i>SvgaHwIoPortUcharString</i> must buffer subsequent instructions from the application and check that none can hang the machine. If the application issues any sequence of instructions that might hang the machine, <i>SvgaHwIoPortUcharString</i> must discard the buffered instructions. Otherwise, it should output them, a UCHAR at a time, to the specified, mapped I/O port.

<i>SvgaHwIoPortUcharString</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564131">EMULATOR_ACCESS_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569908">SVGA Functions</a>



<a href="https://msdn.microsoft.com/91e2dc51-0f3a-4cda-abe6-72893fd4da79">SvgaHwIoPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570366">VideoPortSetTrappedEmulatorPorts</a>
 

 

