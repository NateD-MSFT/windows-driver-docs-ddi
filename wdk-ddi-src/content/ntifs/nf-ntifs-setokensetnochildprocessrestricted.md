---
UID: NF.ntifs.SeTokenSetNoChildProcessRestricted
title: SeTokenSetNoChildProcessRestricted function
author: windows-driver-content
description: The SeTokenSetNoChildProcessRestricted routine sets the TOKEN_AUDIT_NO_CHILD_PROCESS or TOKEN_AUDIT_NO_CHILD_PROCESS flags in the token.
old-location: ifsk\setokensetnochildprocessrestricted.htm
old-project: ifsk
ms.assetid: FCFCBF4C-CBAA-4284-A6F4-67630608CF19
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SeTokenSetNoChildProcessRestricted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeTokenSetNoChildProcessRestricted
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
---

# SeTokenSetNoChildProcessRestricted function



## -description
The <b>SeTokenSetNoChildProcessRestricted</b> routine sets the <b>TOKEN_AUDIT_NO_CHILD_PROCESS</b> or <b>TOKEN_AUDIT_NO_CHILD_PROCESS</b>
    flags in the token.  



## -syntax

````
void NTKERNELAPI SeTokenSetNoChildProcessRestricted(
  _In_ PACCESS_TOKEN Token,
  _In_ PBOOLEAN      UnlessSecure,
  _In_ PBOOLEAN      AuditOnly
);
````


## -parameters

### -param Token [in]

Specifies a pointer to the access token.


### -param UnlessSecure [in]

A pointer to a boolean that indicates that secure process creation shoudl always be enabled.


### -param AuditOnly [in]

A pointer to a boolean that indicates if the mitigation should be enabled in
                audit-only mode.


## -returns
This function does not return a value.


## -remarks
Note that both flags cannot be set at the same time
    and it is possible to upgrade from audit-only mode to enforcement
    mode but not vice-versa.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10, version 1709.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.setokengetnochildprocessrestricted">SeTokenGetNoChildProcessRestricted</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeTokenSetNoChildProcessRestricted function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
