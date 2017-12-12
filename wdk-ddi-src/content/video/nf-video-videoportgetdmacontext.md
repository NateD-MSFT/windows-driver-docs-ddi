---
UID: NF.video.VideoPortGetDmaContext
title: VideoPortGetDmaContext function
author: windows-driver-content
description: The VideoPortGetDmaContext function is obsolete in Windows 2000 and later.VideoPortGetDmaContext gets the context previously associated with the specified DMA handle.
old-location: display\videoportgetdmacontext.htm
old-project: display
ms.assetid: 1bd9a156-a366-4f35-956f-d195c41ae722
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VideoPortGetDmaContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortGetDmaContext
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: 
req.product: Windows 10 or later.
---

# VideoPortGetDmaContext function



## -description
The <b>VideoPortGetDmaContext</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortGetDmaContext</b> gets the context previously associated with the specified DMA handle.



## -syntax

````
PVOID VideoPortGetDmaContext(
  _In_ PVOID HwDeviceExtension,
  _In_ PDMA  pDma
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pDma [in]

Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="display.videoportlockpages">VideoPortLockPages</a> returns. 


## -returns
<b>VideoPortGetDmaContext</b> always returns <b>NULL</b>.


## -remarks
See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.


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
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
</table>