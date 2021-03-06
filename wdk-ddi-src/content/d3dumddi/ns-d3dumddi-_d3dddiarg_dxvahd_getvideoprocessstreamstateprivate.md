---
UID: NS:d3dumddi._D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
title: "_D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE"
author: windows-driver-content
description: The D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure describes the private stream-state of the video processor to retrieve.
old-location: display\d3dddiarg_dxvahd_getvideoprocessstreamstateprivate.htm
old-project: display
ms.assetid: f55dc37a-fb67-48fe-8e32-29b2e71b6abc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure [Display Devices], UMDisplayDriver_param_Structs_5c255d85-4e9e-4a3f-a782-3fd96dbcd0d9.xml, _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, d3dumddi/D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE, display.d3dddiarg_dxvahd_getvideoprocessstreamstateprivate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE
---

# _D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure


## -description


The D3DDDIARG_DXVAHD_GETVIDEOPROCESSSTREAMSTATEPRIVATE structure describes the private stream-state of the video processor to retrieve. 


## -struct-fields




### -field hVideoProcessor

[in] A handle to the video processor whose private stream-state is the runtime requests.


### -field StreamNumber

[in] A zero-based stream index number. This number must be less than the number that the driver set in the <b>MaxStreamStates</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a> structure. 


### -field pData

[in/out] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563098">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure that identifies the private stream state to retrieve. The driver uses DXVAHDDDI_STREAM_STATE_PRIVATE_DATA to return the private stream-state data. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563098">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563113">DXVAHDDDI_VPDEVCAPS</a>



<a href="https://msdn.microsoft.com/0503b382-8ed3-461e-906f-27953ac5f757">GetVideoProcessStreamStatePrivate</a>
 

 

