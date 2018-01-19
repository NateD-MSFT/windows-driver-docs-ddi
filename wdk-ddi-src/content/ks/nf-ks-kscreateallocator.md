---
UID : NF:ks.KsCreateAllocator
title : KsCreateAllocator function
author : windows-driver-content
description : The KsCreateAllocator function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.
old-location : stream\kscreateallocator.htm
old-project : stream
ms.assetid : c67e036c-9f4c-447e-94bb-73cf215c865a
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsCreateAllocator
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsCreateAllocator
req.alt-loc : ks.lib,ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : PASSIVE_LEVEL (See Remarks section)
req.typenames : 
---


# KsCreateAllocator function
The <b>KsCreateAllocator</b> function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP.

## Syntax

````
NTSTATUS KsCreateAllocator(
  _In_  HANDLE               ConnectionHandle,
  _In_  PKSALLOCATOR_FRAMING AllocatorFraming,
  _Out_ PHANDLE              AllocatorHandle
);
````

## Parameters

`ConnectionHandle`

Specifies the handle to the sink connection on which to create the allocator.

`AllocatorFraming`

Specified framing for the allocator.

`AllocatorHandle`

Specifies the pointer to a handle to store the allocator handle.


## Return Value

The <b>KsCreateAllocator</b> function returns STATUS_SUCCESS if successful, or it returns an error if unsuccessful.

## Remarks

There are two versions of the <b>KsCreateAllocator</b> function: one for user-mode clients and one for kernel-mode clients. This function can only be called at PASSIVE_LEVEL for kernel-mode clients.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL (See Remarks section) |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\ns-ks-ksallocator_framing.md">KSALLOCATOR_FRAMING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateAllocator function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>