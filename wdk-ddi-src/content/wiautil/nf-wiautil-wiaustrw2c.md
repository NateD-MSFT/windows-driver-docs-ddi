---
UID : NF:wiautil.wiauStrW2C
title : wiauStrW2C function
author : windows-driver-content
description : The wiauStrW2C function converts a Unicode string to an ANSI character string.
old-location : image\wiaustrw2c.htm
old-project : image
ms.assetid : 53657c26-5007-4c8e-aadf-5d464f1222d2
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : wiauStrW2C
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wiautil.h
req.include-header : Wiautil.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : wiauStrW2C
req.alt-loc : wiautil.h
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
req.typenames : SKIP_AMOUNT
req.product : Windows 10 or later.
---


# wiauStrW2C function
The <b>wiauStrW2C</b> function converts a Unicode string to an ANSI character string.

## Syntax

````
HRESULT _stdcall wiauStrW2C(
  _In_  WCHAR *pwszSrc,
  _Out_ CHAR  *pszDst,
        INT   iSize
);
````

## Parameters

`pwszSrc`

Points to the Unicode string to be converted.

`pszDst`

Pointer to a memory location that receives the converted ANSI string.

`iSize`

Specifies the size, in bytes, of the buffer pointed to by <i>pszDst</i>.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wiautil\nf-wiautil-wiaustrc2c.md">wiauStrC2C</a>
</dt>
<dt>
<a href="..\wiautil\nf-wiautil-wiaustrc2w.md">wiauStrC2W</a>
</dt>
<dt>
<a href="..\wiautil\nf-wiautil-wiaustrw2w.md">wiauStrW2W</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauStrW2C function%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>