---
UID: NF.engextcpp.ExtRemoteTyped.GetTypeFieldOffset
title: ExtRemoteTyped::GetTypeFieldOffset method
author: windows-driver-content
description: The GetTypeFieldOffset static method returns the offset of a member within a structure.
old-location: debugger\extremotetyped_gettypefieldoffset.htm
old-project: Debugger
ms.assetid: 5f966bf0-2dc3-4422-bfec-09d1b136f9f0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ExtRemoteTyped, ExtRemoteTyped::GetTypeFieldOffset, GetTypeFieldOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtRemoteTyped.GetTypeFieldOffset
req.alt-loc: engextcpp.hpp
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

# ExtRemoteTyped::GetTypeFieldOffset method



## -description
The <b>GetTypeFieldOffset</b> static method returns the offset of a member within a structure.



## -syntax

````
static ULONG GetTypeFieldOffset(
  [in] PCSTR Type,
  [in] PCSTR Field
);
````


## -parameters

### -param Type [in]

The name of the type of the structure. This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.


### -param Field [in]

The name of the member in the structure.  You can specify sub-members  by using a dot operator (.) (for example, <b>mymember.mysubmember</b>).


## -returns
<b>GetTypeFieldOffset</b> returns the number of bytes between the address of an instance of the structure and address of the instance's member.


## -remarks


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
<dt>Engextcpp.hpp (include Engextcpp.hpp)</dt>
</dl>
</td>
</tr>
</table>