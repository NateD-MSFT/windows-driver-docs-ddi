---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0033
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0033
author: windows-driver-content
description: The device functions of video.
old-location: display\d3d12ddi-device-funcs-video-0033.htm
old-project: display
ms.assetid: faaaf6e5-9f4d-4051-a656-92c1394cda24
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0033, D3D12DDI_DEVICE_FUNCS_VIDEO_0033 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO_0033, display.d3d12ddi-device-funcs-video-0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
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
-	d3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0033
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0033
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0033 structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The device functions of video.


## -struct-fields




### -field pfnGetCaps

Get caps.


### -field pfnCalcPrivateVideoDecoderSize

Calculates the private video decoder size.


### -field pfnCreateVideoDecoder

Creates a video decoder.


### -field pfnDestroyVideoDecoder

Destroys the video decoder.


### -field pfnCalcPrivateVideoDecoderHeapSize

Calculates the private video decoder heap size.


### -field pfnCreateVideoDecoderHeap

Creates the video decoder heap.


### -field pfnDestroyVideoDecoderHeap

Destroys the video decoder heap.


### -field pfnCalcPrivateVideoProcessorSize

Calculates the private video processor size.


### -field pfnCreateVideoProcessor

Creates the video processor.


### -field pfnDestroyVideoProcessor

Destroys the video processor.

