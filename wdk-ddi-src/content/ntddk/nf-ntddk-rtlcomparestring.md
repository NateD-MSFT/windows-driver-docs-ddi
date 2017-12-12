---
UID: NF.ntddk.RtlCompareString
title: RtlCompareString function
author: windows-driver-content
description: The RtlCompareString routine compares two counted strings.
old-location: kernel\rtlcomparestring.htm
old-project: kernel
ms.assetid: 59d023d4-a2b4-4183-9572-cb48621c76fb
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlCompareString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlCompareString
req.alt-loc: NtosKrnl.exe,Ntdll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
---

# RtlCompareString function



## -description
The <b>RtlCompareString</b> routine compares two counted strings. 



## -syntax

````
LONG RtlCompareString(
  _In_ const STRING  *String1,
  _In_ const STRING  *String2,
  _In_       BOOLEAN CaseInSensitive
);
````


## -parameters

### -param String1 [in]

Pointer to the first string.


### -param String2 [in]

Pointer to the second string.


### -param CaseInSensitive [in]

If <b>TRUE</b>, case should be ignored when doing the comparison.


## -returns
<b>RtlCompareString</b> returns a signed value that gives the results of the comparison:
<dl>
<dt><b>Zero</b></dt>
</dl><i>String1</i> equals <i>String2</i>.
<dl>
<dt><b>&lt; Zero</b></dt>
</dl><i>String1</i> is less than <i>String2</i>.
<dl>
<dt><b>&gt; Zero </b></dt>
</dl><i>String1</i> is greater than <i>String2</i>.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe (kernel mode); </dt>
<dt>Ntdll.dll (user mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlcompareunicodestring">RtlCompareUnicodeString</a>
</dt>
<dt>
<a href="kernel.rtlequalstring">RtlEqualString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCompareString routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
