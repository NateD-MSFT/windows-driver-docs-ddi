---
UID: NC.ndis.PROTOCOL_CL_CLOSE_AF_COMPLETE
title: PROTOCOL_CL_CLOSE_AF_COMPLETE
author: windows-driver-content
description: The ProtocolClCloseAfComplete function is used by connection-oriented NDIS clients.
old-location: netvista\protocolclcloseafcomplete.htm
old-project: netvista
ms.assetid: 7597e124-34e4-4326-98b3-c65dbe90ae6f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClCloseAfComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClCloseAfComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClCloseAfComplete
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# PROTOCOL_CL_CLOSE_AF_COMPLETE callback



## -description
The 
  <i>ProtocolClCloseAfComplete</i> function is used by connection-oriented NDIS clients. All
  connection-oriented NDIS clients must have 
  <i>ProtocolClCloseAfComplete</i> functions to complete the asynchronous operations that they initiate with 
  <a href="netvista.ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>.



## -prototype

````
PROTOCOL_CL_CLOSE_AF_COMPLETE ProtocolClCloseAfComplete;

VOID ProtocolClCloseAfComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE ProtocolAfContext
)
{ ... }
````


## -parameters

### -param Status [in]

Specifies the final status of the client-initiated request to close the address family, which can
     be one of the following:
     




### -param NDIS_STATUS_SUCCESS

The address family was closed. The 
       <i>NdisAfHandle</i> that represented the open address family, which the client stored in its 
       <i>ProtocolAfContext</i> area, is now invalid.


### -param NDIS_STATUS_FAILURE

Either the AF has associated VC(s) and/or registered SAP(s) that the client must release before
       attempting to close the AF, or the client called 
       <b>NdisClCloseAddressFamily</b> twice because NDIS discovered that the AF state was marked as
       "closing."

</dd>
</dl>

### -param ProtocolAfContext [in]

Specifies the client-supplied handle to its per-AF context area. The client originally set up this
     context area and passed this handle to NDIS with 
     <b>NdisClOpenAddressFamilyEx</b>.


## -returns
None


## -remarks
After ensuring that it has no outstanding VCs and/or registered SAPs on its open address family, a
    client calls 
    <a href="netvista.ndisclcloseaddressfamily">NdisClCloseAddressFamily</a> to
    delete the association between itself, a call manager, and a particular underlying NIC. NDIS calls the 
    <i>ProtocolCmCloseAf</i> function for the call manager that this client originally used to open the
    address family as an asynchronous operation. After calling 
    <b>NdisClCloseAddressFamily</b>, the client should consider the 
    <i>NdisAfHandle</i> invalid.

Consequently, the client must have a 
    <i>ProtocolClCloseAfComplete</i> function, which NDIS calls when the asynchronous close-AF operation is
    done. If the input 
    <i>Status</i> is NDIS_STATUS_SUCCESS, the client can release its per-AF context area.

To define a <i>ProtocolClCloseAfComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClCloseAfComplete</i> function that is named "MyClCloseAfComplete", use the <b>PROTOCOL_CL_CLOSE_AF_COMPLETE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CL_CLOSE_AF_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_CLOSE_AF_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/a5aa62d6-7851-4efd-9eee-0fdc3bb5a2ad">ProtocolClCloseAfComplete
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>ProtocolClCloseAfComplete
   (NDIS 5.1)</i>) in Windows XP.

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
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisclcloseaddressfamily">NdisClCloseAddressFamily</a>
</dt>
<dt>
<a href="netvista.ndisclopenaddressfamilyex">NdisClOpenAddressFamilyEx</a>
</dt>
<dt>
<a href="netvista.ndisfreememory">NdisFreeMemory</a>
</dt>
<dt>
<a href="netvista.ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_unbind_adapter_ex.md">ProtocolUnbindAdapterEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_CLOSE_AF_COMPLETE callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
