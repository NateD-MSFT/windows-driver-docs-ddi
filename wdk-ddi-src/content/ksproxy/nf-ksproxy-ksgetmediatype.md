---
UID : NF:ksproxy.KsGetMediaType
title : KsGetMediaType function
author : windows-driver-content
description : The KsGetMediaType function retrieves information about a media type on a pin factory identifier.
old-location : stream\ksgetmediatype.htm
old-project : stream
ms.assetid : 4b7aac38-ab29-4cac-a7f0-896423b17400
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsGetMediaType
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsGetMediaType
req.alt-loc : Ksproxy.lib,Ksproxy.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ksproxy.lib
req.dll : 
req.irql : 
req.typenames : PIPE_STATE
---


# KsGetMediaType function
The <b>KsGetMediaType</b> function retrieves information about a media type on a pin factory identifier.

## Syntax

````
HRESULT KsGetMediaType(
  _In_  int           Position,
  _Out_ AM_MEDIA_TYPE *AmMediaType,
  _In_  HANDLE        FilterHandle,
  _In_  ULONG         PinFactoryId
);
````

## Parameters

`Position`

Offset into the data range item that <b>KsGetMediaType</b> fills. Note that the data type of <i>Position</i> is <b>int</b> to conform to underlying calls.

`AmMediaType`

Pointer to a variable that receives information in a AM_MEDIA_TYPE structure.

`FilterHandle`

Handle to the filter that contains the pin factory to query.

`PinFactoryId`

Identifier of the pin factory against which the information for a media type is being returned.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.

## Remarks

The <b>KsGetMediaType</b> function queries the list of data ranges and performs a data intersection on the specified data range, thus producing a data format. It then converts that data format to a media type.

For more information about AM_MEDIA_TYPE, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ksproxy\nn-ksproxy-ikspinfactory.md">IKsPinFactory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetMediaType function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>