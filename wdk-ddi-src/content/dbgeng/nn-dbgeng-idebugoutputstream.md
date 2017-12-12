---
UID: NN.dbgeng.IDebugOutputStream
title: IDebugOutputStream
author: windows-driver-content
description: Supports the debug output stream.
old-location: debugger\idebugoutputstream.htm
old-project: debugger
ms.assetid: 7A9AB25B-2B8B-4E8A-9E67-79C56181E5D9
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DebugCreateEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugOutputStream
req.alt-loc: dbgeng.h
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

# IDebugOutputStream interface



## -description
Supports the debug output stream.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugOutputStream</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDebugOutputStream</b> also has these types of members:

The <b>IDebugOutputStream</b> interface has these methods.

Writes to the debug output stream.

 


## -members
The <b>IDebugOutputStream</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="debugger.idebugoutputstream_write">Write</a>
</td>
<td align="left" width="63%">
Writes to the debug output stream.

</td>
</tr>
</table>Writes to the debug output stream.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>