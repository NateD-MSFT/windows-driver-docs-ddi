---
UID: NS.D3D10UMDDI.D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
author: windows-driver-content
description: Contains input data for the QueryAuthenticatedChannel(D3D11_1) function.
old-location: display\d3d11_1ddi_authenticated_query_input.htm
old-project: display
ms.assetid: f7a4fb53-aa01-4279-a59a-fd92b0ceeab7
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_INPUT, D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_AUTHENTICATED_QUERY_INPUT
req.alt-loc: D3d10umddi.h
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

# D3D11_1DDI_AUTHENTICATED_QUERY_INPUT structure



## -description
Contains input data for the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a> function.



## -syntax

````
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_INPUT {
  GUID   QueryType;
  HANDLE hChannel;
  UINT   SequenceNumber;
} D3D11_1DDI_AUTHENTICATED_QUERY_INPUT;
````


## -struct-fields

### -field QueryType

A GUID that specifies the query. The following GUIDs are defined.


### -field D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ATTRIBUTES

<dd>
Returns the type of I/O bus that is used to send data to the GPU.

Output data structure: 


<a href="display.D3D11_1DDI_authenticated_query_acessibility_output">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE

<dd>
Returns the type of authenticated channel.

Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406386">D3D11_1DDI_AUTHENTICATED_QUERY_CHANNEL_TYPE_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION

<dd>
Returns handles to the cryptographic session and Direct3D device that are associated with a specified DirectX Video Acceleration 2 (DXVA-2) decode device.

Input data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406388">D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_INPUT</a>


Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406390">D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_CURRENT_ENCRYPTION_WHEN_ACCESSIBLE

<dd>
Returns the encryption type that is applied before content becomes accessible to the CPU or bus.

Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406378">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_DEVICE_HANDLE

<dd>
Returns a handle to the device that is associated with this authenticated channel.

Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406396">D3D11_1DDI_AUTHENTICATED_QUERY_DEVICE_HANDLE_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID

<dd>
Returns one of the encryption types that can be used to encrypt content before it becomes accessible to the CPU or bus.

Input data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406380">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_INPUT</a>


Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406382">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_ENCRYPTION_WHEN_ACCESSIBLE_GUID_COUNT

<dd>
Returns the number of encryption types that can be used to encrypt content before it becomes accessible to the CPU or bus.

Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406378">D3D11_1DDI_AUTHENTICATED_QUERY_ACCESSIBILITY_ENCRYPTION_GUID_COUNT_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID

<dd>
Returns one of the output identifiers that is associated with a specified cryptographic session and Direct3D device.

Input data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406412">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_INPUT</a>


Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406415">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT

<dd>
Returns the number of output identifiers that are associated with a specified cryptographic session and Direct3D device.

Input data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406406">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_INPUT</a>


Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406409">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT_ID_COUNT_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_PROTECTION

<dd>
Returns the current protection level for the device.

Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406419">D3D11_1DDI_AUTHENTICATED_QUERY_PROTECTION_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS

<dd>
Returns information about a process that is allowed to open shared resources with restricted access.

Input data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406426">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_INPUT</a>


Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406429">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_COUNT

<dd>
Returns the number of processes that are allowed to open shared resources with restricted access.

Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406423">D3D11_1DDI_AUTHENTICATED_QUERY_RESTRICTED_SHARED_RESOURCE_PROCESS_COUNT_OUTPUT</a>



### -field D3D11_1DDI_AUTHENTICATED_QUERY_UNRESTRICTED_PROTECTED_SHARED_RESOURCE_COUNT

<dd>
Returns the number of protected shared resources that can be opened by any process with no restrictions.

Output data structure: <a href="https://msdn.microsoft.com/library/windows/hardware/hh406431">D3D11_1DDI_AUTHENTICATED_QUERY_UNRESTRICTED_PROTECTED_SHARED_RESOURCE_COUNT_OUTPUT</a>


</dd>
</dl>

### -field hChannel

A handle to the authenticated channel. This handle was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a> function.


### -field SequenceNumber

The query sequence number. At the start of the session, generate a cryptographically secure 32-bit random number to use as the starting sequence number. For each query, increment the sequence number by 1.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createauthenticatedchannel.md">CreateAuthenticatedChannel(D3D11_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel(D3D11_1)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_AUTHENTICATED_QUERY_INPUT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
