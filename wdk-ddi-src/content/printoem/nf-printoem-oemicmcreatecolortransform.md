---
UID : NF:printoem.OEMIcmCreateColorTransform
title : OEMIcmCreateColorTransform function
author : windows-driver-content
description : The OEMIcmCreateColorTransform function creates an ICM color transform.
old-location : print\oemicmcreatecolortransform.htm
old-project : print
ms.assetid : 995fdac4-e958-4eed-ba3a-7be0349dec59
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : OEMIcmCreateColorTransform
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : printoem.h
req.include-header : Printoem.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : OEMIcmCreateColorTransform
req.alt-loc : printoem.h
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
req.typenames : STDVARIABLEINDEX
req.product : Windows 10 or later.
---


# OEMIcmCreateColorTransform function
The <code>OEMIcmCreateColorTransform</code> function creates an ICM color transform.

## Syntax

````
HANDLE APIENTRY OEMIcmCreateColorTransform(
           DHPDEV                                   dhpdev,
           LPLOGCOLORSPACEW                         pLogColorSpace,
  _In_opt_ _reads_bytes_(cjSourceProfile) PVOID     pvSourceProfile,
           ULONG                                    cjSourceProfile,
  _In_     _reads_bytes_(cjDestProfile) PVOID       pvDestProfile,
           ULONG                                    cjDestProfile,
  _In_opt_ _reads_bytes_opt_(cjTargetProfile) PVOID pvTargetProfile,
           ULONG                                    cjTargetProfile,
           POINTL                                   dwReserved
);
````

## Parameters

`dhpdev`



`pLogColorSpace`



`pvSourceProfile`



`cjSourceProfile`



`pvDestProfile`



`cjDestProfile`



`pvTargetProfile`



`cjTargetProfile`



`dwReserved`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printoem.h (include Printoem.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |