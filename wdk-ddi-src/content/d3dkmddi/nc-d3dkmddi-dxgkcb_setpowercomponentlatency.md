---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTLATENCY
title: DXGKCB_SETPOWERCOMPONENTLATENCY
author: windows-driver-content
description: Called by the display miniport driver to set the latency tolerance for a power component of type DXGK_POWER_COMPONENT_OTHER.
old-location: display\dxgkcbsetpowercomponentlatency.htm
old-project: display
ms.assetid: 8FF86746-15A2-4BDF-98AF-23B5F9960DB9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKCB_SETPOWERCOMPONENTLATENCY, DxgkCbSetPowerComponentLatency, DxgkCbSetPowerComponentLatency callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentLatency, display.dxgkcbsetpowercomponentlatency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkCbSetPowerComponentLatency
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_SETPOWERCOMPONENTLATENCY callback


## -description


Called by the display miniport driver to set the latency tolerance for a power component of type <b>DXGK_POWER_COMPONENT_OTHER</b>.


## -parameters




### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -param ComponentIndex

The power component index specified by  <a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.


### -param Latency

The <i>latency tolerance</i>—the maximum  time, in units of 100 nanoseconds, that the display miniport driver should take to awaken a power component from an idle state. The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> uses this information to select an appropriate idle state for the component that does not violate the requested latency tolerance. The latency tolerance specified by <i>Latency</i> remains in effect until the driver calls this function again to update it.

For more information, see Remarks.


## -returns



This callback function does not return a value.




## -remarks



<div class="alert"><b>Note</b>  The display miniport driver should call this function only if the component type is <b>DXGK_POWER_COMPONENT_OTHER</b>. The Microsoft DirectX graphics kernel subsystem sets the latency tolerance value for other component types.</div>
<div> </div>
If the power component is in an idle state when this function is called, the <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> might change the component's F-state to meet the latency tolerance specified by <i>Latency</i>.

If the driver sets <i>Latency</i> to a value of <b>PO_FX_UNKNOWN_TIME</b> (defined in Wdm.h), the Power Engine Plug-in (PEP) might be unable to set the component to an F-state lower than F0.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>
 

 

