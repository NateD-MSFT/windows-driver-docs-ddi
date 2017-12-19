---
UID: NF.dbgeng.IDebugBreakpoint2.GetType
title: IDebugBreakpoint2::GetType method
author: windows-driver-content
description: The GetType method returns the type of the breakpoint and the type of the processor that a breakpoint is set for.
old-location: debugger\gettype.htm
old-project: Debugger
ms.assetid: c6aa6560-3183-4e3a-a625-80d1c5072af5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugBreakpoint2, IDebugBreakpoint2::GetType, GetType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugBreakpoint.GetType,IDebugBreakpoint2.GetType
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

# IDebugBreakpoint2::GetType method



## -description
The <b>GetType</b> method returns the type of the breakpoint and the type of the processor that a breakpoint is set for.



## -syntax

````
HRESULT GetType(
  [out] PULONG BreakType,
  [out] PULONG ProcType
);
````


## -parameters

### -param BreakType [out]

The type of the breakpoint.  The type can be one of the following  values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_CODE

</td>
<td>
Software breakpoint

</td>
</tr>
<tr>
<td>
DEBUG_BREAKPOINT_DATA

</td>
<td>
Processor breakpoint

</td>
</tr>
</table>
 


### -param ProcType [out]

The type of the processor that the breakpoint is set for.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
If changes are made to the breakpoint, the processor type might change.

The <a href="debugger.getparameters">GetParameters</a> method also returns the information that is returned in <i>BreakType</i> and <i>ProcType</i>.

For more information about breakpoint types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538928">Breakpoints</a>.


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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>