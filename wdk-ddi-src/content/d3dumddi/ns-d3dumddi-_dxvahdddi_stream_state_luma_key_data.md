---
UID: NS.D3DUMDDI._DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA
title: _DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure describes stream-state data that specifies the luma key of the input. The driver assumes that a pixel that has a luma value within the luma-key range is transparent.
old-location: display\dxvahdddi_stream_state_luma_key_data.htm
old-project: display
ms.assetid: bd620f6d-6c19-41d4-a68c-3dcf2eec93ae
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA, DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA
req.alt-loc: d3dumddi.h
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

# _DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure



## -description
The DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure describes stream-state data that specifies the luma key of the input. The driver assumes that a pixel that has a luma value within the luma-key range is transparent. 



## -syntax

````
typedef struct _DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA {
  BOOL  Enable;
  FLOAT Lower;
  FLOAT Upper;
} DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA;
````


## -struct-fields

### -field Enable

[in] A Boolean value that specifies whether the luma key is enabled. The default value is <b>FALSE</b>, which indicates that the luma key is disabled. 


### -field Lower

[in] A FLOAT value in the 0.0 to 1.0 range that describes the lower luma-key value. The default value is 0.0. 


### -field Upper

[in] A FLOAT value in the 0.0 to 1.0 range that describes the upper luma-key value. The default value is 0.0. 


## -remarks
The Direct3D runtime specifies the DXVAHDDDI_STREAM_STATE_LUMA_KEY state in the <b>State</b> member of the <a href="display.d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a> function. This happens  only when the driver has previously set the DXVAHDDDI_FEATURE_CAPS_LUMA_KEY value in the <b>FeatureCaps</b> member of the <a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set. 

If the driver does not set the DXVAHDDDI_INPUT_FORMAT_CAPS_RGB_LUMA_KEY value in the <b>InputFormatCaps</b> member of the <a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set, the driver ignores the luma-key data.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA is supported beginning with the Windows 7 operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>
</dt>
<dt>
<a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
