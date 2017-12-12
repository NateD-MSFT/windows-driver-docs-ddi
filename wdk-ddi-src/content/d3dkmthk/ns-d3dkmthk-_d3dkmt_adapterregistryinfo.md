---
UID: NS.D3DKMTHK._D3DKMT_ADAPTERREGISTRYINFO
title: _D3DKMT_ADAPTERREGISTRYINFO
author: windows-driver-content
description: The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter.
old-location: display\d3dkmt_adapterregistryinfo.htm
old-project: display
ms.assetid: b1bad6e8-8592-457a-8f66-40fc5040ae96
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_ADAPTERREGISTRYINFO, D3DKMT_ADAPTERREGISTRYINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_ADAPTERREGISTRYINFO
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_ADAPTERREGISTRYINFO structure



## -description
The D3DKMT_ADAPTERREGISTRYINFO structure contains registry information about the graphics adapter. 



## -syntax

````
typedef struct _D3DKMT_ADAPTERREGISTRYINFO {
  WCHAR AdapterString[MAX_PATH];
  WCHAR BiosString[MAX_PATH];
  WCHAR DacType[MAX_PATH];
  WCHAR ChipType[MAX_PATH];
} D3DKMT_ADAPTERREGISTRYINFO;
````


## -struct-fields

### -field AdapterString

[out] A string that contains the name of the graphics adapter.


### -field BiosString

[out] A string that contains the name of the BIOS for the graphics adapter.


### -field DacType

[out] A string that contains the DAC type for the graphics adapter.


### -field ChipType

[out] A string that contains the chip type for the graphics adapter.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="display.d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_ADAPTERREGISTRYINFO structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
