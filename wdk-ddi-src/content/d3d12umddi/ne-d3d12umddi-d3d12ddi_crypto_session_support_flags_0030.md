---
UID: NE.d3d12umddi.D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
title: D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
author: windows-driver-content
description: The crypto session support flags.
old-location: display\d3d12ddi-crypto-session-support-flags-0030.htm
old-project: display
ms.assetid: ffa81a22-3de2-48f8-b753-c296401e0da3
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030, D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030
req.alt-loc: d3d12umddi.h
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

# D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030 enumeration



## -description
The crypto session support flags.



## -syntax

````
typedef enum _D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030 { 
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_NONE,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_SUPPORTED,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_HEADER_DECRYPTION_REQUIRED,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_INDEPENDENT_DECRYPTION_REQUIRED,
  D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_TRANSCRYPTION_REQUIRED
} D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAGS_0030;
````


## -enum-fields

### -field D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_NONE

No flag is defined.


### -field D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_SUPPORTED

The crypto session support flag is supported.


### -field D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_HEADER_DECRYPTION_REQUIRED

The crypto session support flag requires a header decryption.


### -field D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_INDEPENDENT_DECRYPTION_REQUIRED

The crypto session support flag requires an independent decyption.


### -field D3D12DDI_CRYPTO_SESSION_SUPPORT_FLAG_0030_TRANSCRYPTION_REQUIRED

The crypto session support flag requires transcryption.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>