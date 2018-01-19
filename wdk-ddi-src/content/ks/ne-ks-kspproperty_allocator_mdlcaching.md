---
UID : NE:ks.KSPPROPERTY_ALLOCATOR_MDLCACHING
title : KSPPROPERTY_ALLOCATOR_MDLCACHING
author : windows-driver-content
description : This enumeration is used internally by the operating system.
old-location : stream\kspproperty_allocator_mdlcaching.htm
old-project : stream
ms.assetid : 91BB915F-E964-41D9-8D2A-3D5EF6F5B398
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPPROPERTY_ALLOCATOR_MDLCACHING, KSPPROPERTY_ALLOCATOR_MDLCACHING
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ks.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPPROPERTY_ALLOCATOR_MDLCACHING
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
req.typenames : KSPPROPERTY_ALLOCATOR_MDLCACHING
---

# KSPPROPERTY_ALLOCATOR_MDLCACHING Enumeration
This enumeration is used internally by the operating system.

## Syntax
````
typedef enum  { 
  KSPROPERTY_ALLOCATOR_CLEANUP_CACHEDMDLPAGES  = 1
} KSPPROPERTY_ALLOCATOR_MDLCACHING;
````

## Constants

<table>

<tr>
<td>KSPROPERTY_ALLOCATOR_CLEANUP_CACHEDMDLPAGES</td>
<td>This value is used internally by the operating system.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |