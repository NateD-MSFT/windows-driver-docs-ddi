---
UID : NC:wlanihv.DOT11EXT_PRE_ASSOCIATE_COMPLETION
title : DOT11EXT_PRE_ASSOCIATE_COMPLETION
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11extpreassociatecompletion.htm
old-project : netvista
ms.assetid : e617c0ac-0f02-4e15-ba11-81de6331b83d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wlanihv.h
req.include-header : Wlanihv.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : Dot11ExtPreAssociateCompletion
req.alt-loc : wlanihv.h
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
req.typenames : "*LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W"
req.product : Windows 10 or later.
---


# DOT11EXT_PRE_ASSOCIATE_COMPLETION callback function


## Syntax

```
DOT11EXT_PRE_ASSOCIATE_COMPLETION Dot11extPreAssociateCompletion;

DWORD Dot11extPreAssociateCompletion(
  HANDLE hDot11SvcHandle,
  HANDLE hConnectSession,
  DWORD dwReasonCode,
  DWORD dwWin32Error
)
{...}
```

## Parameters

`hDot11SvcHandle`

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.

`hConnectSession`

The handle used by the operating system to reference the connection session with the basic service
     set (BSS) network. This handle value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
     Dot11ExtIhvPerformPreAssociate</a> IHV Handler function.

`dwReasonCode`

A value that provides additional information for the completion status of the pre-association
     operation. The IHV Extensions DLL must set 
     <i>dwReasonCode</i> to an L2_REASON_CODE_xxxx value, which are defined in 
     L2cmn.h.
     

The IHV Extensions DLL returns the general completion status of the pre-association operation through
     the 
     <i>dwWin32Error</i> parameter. Typically, the IHV Extensions DLL sets 
     <i>dwReasonCode</i> to a value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
     L2_REASON_CODE_GROUP_SIZE-1).

`dwWin32Error`

The completion status of the pre-association operation as defined by an error code within 
     Winerror.h. If the operation completes successfully, the IHV Extensions DLL must set 
     <i>dwWin32Error</i> to ERROR_SUCCESS.


## Return Value

If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.

## Remarks

The IHV Extensions DLL must follow these guidelines when calling the 
    <b>Dot11ExtPreAssociateCompletion</b> function.

If the pre-association operation completed successfully, the IHV Extensions DLL must set 
      <i>dwReasonCode</i> to one of the following:

L2_REASON_CODE_SUCCESS.

An IHV-defined value in the range from L2_REASON_CODE_IHV_BASE to (L2_REASON_CODE_IHV_BASE+
        L2_REASON_CODE_GROUP_SIZE-1).

In this situation, the IHV Extensions DLL must set 
      <i>dwWin32Error</i> to ERROR_SUCCESS.

If the pre-association operation completed with a failure, the IHV Extensions DLL must not set 
      <i>dwReasonCode</i> to L2_REASON_CODE_SUCCESS. Instead, the DLL must set 
      <i>dwReasonCode</i> to one of the following:

An appropriate L2_REASON_CODE_xxxx error value.

In this situation, the IHV Extensions DLL must not set 
      <i>dwWin32Error</i> to ERROR_SUCCESS. Instead, the DLL must set 
      <i>dwWin32Error</i> to an appropriate error code defined in 
      Winerror.h

The IHV Extensions DLL must call 
      <b>Dot11ExtPreAssociateCompletion</b> to cancel all pending pre-association
      operations whenever the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a> or 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a> IHV
      Handler functions are called. In this situation, the DLL must set the 
      <i>dwWin32Error</i> parameter to ERROR_CANCELLED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wlanihv.h (include Wlanihv.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_adapter_reset.md">Dot11ExtIhvAdapterReset</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_deinit_adapter.md">Dot11ExtIhvDeinitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_PRE_ASSOCIATE_COMPLETION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>