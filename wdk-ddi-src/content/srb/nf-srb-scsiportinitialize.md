---
UID : NF:srb.ScsiPortInitialize
title : ScsiPortInitialize function
author : windows-driver-content
description : For a non-Plug and Play miniport driver, the ScsiPortInitialize routine sets up the PORT_CONFIGURATION_INFORMATION structure and calls the miniport driver's HwScsiFindAdapter routine.
old-location : storage\scsiportinitialize.htm
old-project : storage
ms.assetid : f6adca68-e016-4725-bd8e-691c71d1d471
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ScsiPortInitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : srb.h
req.include-header : Miniport.h, Scsi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ScsiPortInitialize
req.alt-loc : Scsiport.lib,Scsiport.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Scsiport.lib
req.dll : 
req.irql : 
req.typenames : "*PSPB_CONTROLLER_CONFIG, SPB_CONTROLLER_CONFIG"
req.product : Windows 10 or later.
---


# ScsiPortInitialize function
For a non-Plug and Play miniport driver, the <b>ScsiPortInitialize</b> routine sets up the PORT_CONFIGURATION_INFORMATION structure and calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine. <b>ScsiPortInitialize</b> also sets up system objects and resources on behalf of miniport drivers. For a Plug and Play miniport driver, <b>ScsiPortInitialize</b> stores the miniport driver's initialization data for future use.

## Syntax

````
ULONG ScsiPortInitialize(
  _In_ PVOID                          Argument1,
  _In_ PVOID                          Argument2,
  _In_ struct _HW_INITIALIZATION_DATA *HwInitializationData,
  _In_ PVOID                          HwContext
);
````

## Parameters

`Argument1`

Pointer to the driver object that the operating system passed to the miniport driver in the first argument of its <b>DriverEntry</b> routine.

`Argument2`

Pointer to some context information that the operating system passed to the miniport driver in the second argument of its <b>DriverEntry</b>.

`HwInitializationData`

Pointer to the initialization and configuration information supplied by <b>DriverEntry</b>.

`HwContext`

Specifies the address of a context value to be passed to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine. Only legacy miniport drivers that scan the bus for HBAs rather than receiving configuration information from the port driver can use this parameter to store state between calls to <i>HwScsiFindAdapter</i>.


## Return Value

<b>ScsiPortInitialize</b> returns a status value that is used as the return value from the miniport driver's <b>DriverEntry</b> routine.

## Remarks

Every miniport driver's <b>DriverEntry</b> routine must call <b>ScsiPortInitialize</b> after the miniport driver has first zeroed and then set up the HW_INITIALIZATION_DATA.

If a miniport driver can support HBAs on different types of I/O buses, such as both <b>Isa</b> and <b>MicroChannel</b> type I/O buses, the miniport driver should call <b>ScsiPortInitialize</b> for each supported interface type.

A miniport driver that calls <b>ScsiPortInitialize</b> more than once should check the value returned by <b>ScsiPortInitialize</b> at each call and save the lowest value for all its calls. The <b>DriverEntry</b> routine must return the lowest value when it returns control to the system. Miniport driver writers can make no assumptions about the values returned by <b>ScsiPortInitialize</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff552654">DriverEntry of SCSI Miniport Driver</a>
</dt>
<dt>
<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA (SCSI)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiPortInitialize routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>