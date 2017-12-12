---
UID: NF.ntintsafe.RtlLongToUIntPtr
title: RtlLongToUIntPtr function
author: windows-driver-content
description: Converts a value of type LONG to a value of type UINT_PTR.
old-location: kernel\rtllongtouintptr.htm
old-project: kernel
ms.assetid: 901DA09A-ED1C-4884-AE4A-2D251942754C
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlLongToUIntPtr
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
req.alt-api: RtlLongToUIntPtr
req.alt-loc: Ntintsafe.h
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
---

# RtlLongToUIntPtr function



## -description
Converts a value of type <b>LONG</b> to a value of type <b>UINT_PTR</b>.



## -syntax

````
NTSTATUS RtlLongToUIntPtr(
  _In_  LONG     lOperand,
  _Out_ UINT_PTR *puResult
);
````


## -parameters

### -param lOperand [in]

The value to be converted.


### -param puResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>