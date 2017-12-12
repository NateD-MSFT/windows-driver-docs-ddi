---
UID: NF.ndis.NdisAllocateNetBufferMdlAndData
title: NdisAllocateNetBufferMdlAndData function
author: windows-driver-content
description: NDIS drivers call the NdisAllocateNetBufferMdlAndData function to allocate a NET_BUFFER structure along with the associated MDL and data.
old-location: netvista\ndisallocatenetbuffermdlanddata.htm
old-project: netvista
ms.assetid: cfac9061-a685-4e67-aaa2-ca43b7e36cfa
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisAllocateNetBufferMdlAndData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisAllocateNetBufferMdlAndData
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_NetBuffer_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisAllocateNetBufferMdlAndData function



## -description
NDIS drivers call the 
  <b>NdisAllocateNetBufferMdlAndData</b> function to allocate a NET_BUFFER structure along with the associated
  MDL and data.



## -syntax

````
PNET_BUFFER NdisAllocateNetBufferMdlAndData(
  _In_ NDIS_HANDLE PoolHandle
);
````


## -parameters

### -param PoolHandle [in]

A NET_BUFFER structure pool handle that was previously returned from a call to the 
     <b>NdisAllocateNetBufferPool</b> function.


## -returns
<b>NdisAllocateNetBufferMdlAndData</b> returns a pointer to the NET_BUFFER structure that NDIS allocated.
     If the allocation was unsuccessful, this pointer is <b>NULL</b>.


## -remarks
The caller must call the 
    <b>NdisAllocateNetBufferPool</b> function and specify the maximum size of the data buffers. Given this
    value, NDIS can preallocate buffers for the caller.

This function allocates a 
    <a href="netvista.net_buffer">NET_BUFFER</a> structure, MDL and data in a single
    memory buffer. This is useful to achieve high performance when NET_BUFFER structures are frequently
    allocated and freed. The caller should not call 
    <a href="netvista.ndisallocatenetbuffer">NdisAllocateNetBuffer</a> to allocate
    NET_BUFFERs out of NET_BUFFER pools which contain data.

NDIS uses the 
    <i>PoolHandle</i> parameter to get a block of memory, and then creates the NET_BUFFER, MDL, and data
    buffer.

To free the NET_BUFFER and associated information, call the 
    <a href="netvista.ndisfreenetbuffer">NdisFreeNetBuffer</a> function.


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
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_netbuffer_function">Irql_NetBuffer_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisallocatenetbuffer">NdisAllocateNetBuffer</a>
</dt>
<dt>
<a href="netvista.ndisfreenetbuffer">NdisFreeNetBuffer</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateNetBufferMdlAndData function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
