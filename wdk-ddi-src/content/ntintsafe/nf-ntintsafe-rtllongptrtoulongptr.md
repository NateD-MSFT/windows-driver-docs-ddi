---
UID: NF:ntintsafe.RtlLongPtrToULongPtr
title: RtlLongPtrToULongPtr function
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type ULONG_PTR.
old-location: kernel\rtllongptrtoulongptr.htm
old-project: kernel
ms.assetid: 9171C016-D54C-4BF4-BBD7-00D39C062929
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlLongPtrToULongPtr, RtlLongPtrToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtllongptrtoulongptr, ntintsafe/RtlLongPtrToULongPtr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
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
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlLongPtrToULongPtr
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongPtrToULongPtr function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>ULONG_PTR</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param pulResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLongPtrToDWordPtr
</li>
<li>RtlLongPtrToSIZET
</li>
<li>RtlSSIZETToULongPtr
</li>
<li>RtlSSIZETToDWordPtr
</li>
<li>RtlSSIZETToSIZET
</li>
</ul>


