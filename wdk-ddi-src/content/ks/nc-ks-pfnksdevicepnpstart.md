---
UID : NC:ks.PFNKSDEVICEPNPSTART
title : PFNKSDEVICEPNPSTART
author : windows-driver-content
description : An AVStream minidriver's AVStrMiniDeviceStart routine is called when an IRP_MN_START_DEVICE request is sent for a specified device.
old-location : stream\avstrminidevicestart.htm
old-project : stream
ms.assetid : 5a09a8b1-7a20-42e3-a58d-ecd4e7a0558e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : NpdBrokerUninitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ks.h
req.include-header : Ks.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : AVStrMiniDeviceStart
req.alt-loc : ks.h
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
req.typenames : KEYWORDSELECTOR
---


# PFNKSDEVICEPNPSTART callback function
An AVStream minidriver's <i>AVStrMiniDeviceStart</i> routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request is sent for a specified device.

## Syntax

```
PFNKSDEVICEPNPSTART Pfnksdevicepnpstart;

NTSTATUS Pfnksdevicepnpstart(
  PKSDEVICE Device,
  PIRP Irp,
  PCM_RESOURCE_LIST TranslatedResourceList,
  PCM_RESOURCE_LIST UntranslatedResourceList
)
{...}
```

## Parameters

`Device`

Pointer to a <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> structure describing the device to be started.

`Irp`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> that was received.

`TranslatedResourceList`

Pointer to a <a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure that contains the translated resource list extracted from <i>Irp</i>. Equals <b>NULL</b> if <i>Device</i> has no assigned resources. Optional.

`UntranslatedResourceList`

Pointer to a <a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a> structure that contains the untranslated resource list extracted from <i>Irp</i>. Equals <b>NULL</b> if the <a href="..\ks\ns-ks-_ksdevice.md">KSDEVICE</a> member of this parameter list has no assigned resources. Optional.


## Return Value

Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. The start is guaranteed to succeed if the routine returns a successful status code. Do NOT return STATUS_PENDING.

## Remarks

Specify this routine's address in the <b>Start</b> member of its <a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a> structure.

Typically, this routine is used by minidrivers that must evaluate assigned resources. Resource lists are extracted from <i>Irp</i> for the convenience of the minidriver. A minidriver can parse the resource list to find the interrupt assigned to the device, as well as the physical address of memory resources.

Minidrivers may use this routine to allocate context information to associate with the AVStream device. (This is similar to a minidriver under stream class using the device extension to store context information.)

Note that STATUS_PENDING is not a legal return code from this function.  To perform actions in the context of a worker thread before AVStream has completed start actions such as enabling device interfaces, use a post start dispatch. See <a href="..\ks\nc-ks-pfnksdevice.md">AVStrMiniDevicePostStart</a>.

This routine is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_cm_resource_list.md">CM_RESOURCE_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PFNKSDEVICEPNPSTART routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>