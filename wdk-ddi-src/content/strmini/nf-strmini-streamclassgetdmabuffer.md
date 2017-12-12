---
UID: NF.strmini.StreamClassGetDmaBuffer
title: StreamClassGetDmaBuffer function
author: windows-driver-content
description: The StreamClassGetDmaBuffer routine returns a pointer to the DMA buffer that the class driver allocates for the minidriver.
old-location: stream\streamclassgetdmabuffer.htm
old-project: stream
ms.assetid: 1b778d94-55e6-4a5f-aa77-739bcf9a8041
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: StreamClassGetDmaBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StreamClassGetDmaBuffer
req.alt-loc: Stream.lib,Stream.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Stream.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# StreamClassGetDmaBuffer function



## -description
The <b>StreamClassGetDmaBuffer</b> routine returns a pointer to the DMA buffer that the class driver allocates for the minidriver.



## -syntax

````
PVOID StreamClassGetDmaBuffer(
  _In_ PVOID HwDeviceExtension
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="stream.hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="stream.streamclassregisterminidriver">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="stream.hw_stream_request_block">HW_STREAM_REQUEST_BLOCK</a>, <a href="stream.hw_stream_object">HW_STREAM_OBJECT</a>, <a href="stream.hw_time_context">HW_TIME_CONTEXT</a>, and <a href="stream.port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


## -returns
<b>StreamClassGetDmaBuffer</b> returns a pointer to the DMA buffer.


## -remarks
The minidriver specifies the size of the DMA buffer in the <b>DmaBufferSize</b> member of its <a href="stream.hw_initialization_data">HW_INITIALIZATION_DATA</a> structure.


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
<dt>Strmini.h (include Strmini.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Stream.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.hw_initialization_data">HW_INITIALIZATION_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassGetDmaBuffer routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
