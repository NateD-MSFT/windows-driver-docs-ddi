---
UID : NC:winsplp.ROUTER_NOTIFY_CALLBACK
title : ROUTER_NOTIFY_CALLBACK
author : windows-driver-content
description : .
old-location : print\router_notify_callback.htm
old-project : print
ms.assetid : 97D8FEEA-B6D7-4AD7-A067-B503AF8F23FF
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : _SCARD_IO_REQUEST, SCARD_IO_REQUEST, *LPSCARD_IO_REQUEST, *PSCARD_IO_REQUEST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : winsplp.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ROUTER_NOTIFY_CALLBACK
req.alt-loc : Winsplp.h
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
req.typenames : SCARD_IO_REQUEST, *LPSCARD_IO_REQUEST, *PSCARD_IO_REQUEST
req.product : Windows 10 or later.
---


# ROUTER_NOTIFY_CALLBACK callback function


## Syntax

```
ROUTER_NOTIFY_CALLBACK RouterNotifyCallback;

BOOL RouterNotifyCallback(
  DWORD dwCommand,
  PVOID pContext,
  DWORD dwColor,
  PPRINTER_NOTIFY_INFO pNofityInfo,
  DWORD fdwFlags,
  PDWORD pdwResult
)
{...}
```

## Parameters

`dwCommand`



`pContext`



`dwColor`



`pNofityInfo`



`fdwFlags`



`pdwResult`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winsplp.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |