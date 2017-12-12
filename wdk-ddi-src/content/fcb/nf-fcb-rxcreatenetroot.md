---
UID: NF.fcb.RxCreateNetRoot
title: RxCreateNetRoot function
author: windows-driver-content
description: RxCreateNetRoot allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object.
old-location: ifsk\rxcreatenetroot.htm
old-project: ifsk
ms.assetid: 076624d3-96f5-4e93-8598-b880a6b2289b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxCreateNetRoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Rxcontx.h, Mrxfcb.h, Prefix.h, Struchdr.h, Fcb.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxCreateNetRoot
req.alt-loc: fcb.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
---

# RxCreateNetRoot function



## -description
<b>RxCreateNetRoot</b> allocates and initializes a NET_ROOT structure and inserts the name into the net name table on the associated device object. 



## -syntax

````
PNET_ROOT RxCreateNetRoot(
  _In_     PSRV_CALL         SrvCall,
  _In_     PUNICODE_STRING   Name,
  _In_     ULONG             NetRootFlags,
  _In_opt_ PRX_CONNECTION_ID RxConnectionId
);
````


## -parameters

### -param SrvCall [in]

A pointer to the associated SRV_CALL structure.


### -param Name [in]

A pointer to the name to be inserted in the name table.


### -param NetRootFlags [in]

The value to set the <b>Flags</b> member of the NET_ROOT which is used to denote the state of the NET_ROOT structure.


### -param RxConnectionId [in, optional]

A pointer to the connection ID to be associated with the name to be inserted in the prefix name table. This parameter can be <b>NULL</b> in which case no connection ID will be associated with the name inserted in the prefix name table.


## -returns
<b>RxCreateNetRoot</b> returns a pointer to a newly created NET_ROOT data structure on success or a <b>NULL</b> pointer on failure. 


## -remarks
The <b>RxCreateNetRoot</b> routine is not normally called by network mini-redirector drivers directly. RDBSS calls this routine internally when an I/O request packet is received for IRP_MJ_CREATE and a NET_ROOT needs to be created. This IRP is normally received by RDBSS in response to a user-mode application requesting a file create operation on a network share. It is also possible for another kernel driver to issue such an IRP. 

Before calling <b>RxCreateNetRoot</b>, a lock on the name table associated with the device object member of the <i>SrvCall</i> parameter must be acquired in exclusive mode. 

The NET_ROOT flags are split into two groups, those visible to network mini redirectors and those invisible to network mini redirectors. The visible ones are the lower 16-bits of the <b>Flags</b> member of the NET_ROOT. This routine does not check or test which flags are being set. 

On success, the reference count for the SRV_CALL structure is incremented. 


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
<dt>Fcb.h (include Rxcontx.h, Mrxfcb.h, Prefix.h, Struchdr.h, or Fcb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.the_net_root_structure">The NET_ROOT Structure</a>
</dt>
<dt>
<a href="ifsk.rxcreatenetfcb">RxCreateNetFcb</a>
</dt>
<dt>
<a href="ifsk.rxcreatenetfobx">RxCreateNetFobx</a>
</dt>
<dt>
<a href="ifsk.rxcreatesrvcall">RxCreateSrvCall</a>
</dt>
<dt>
<a href="ifsk.rxcreatesrvopen">RxCreateSrvOpen</a>
</dt>
<dt>
<a href="ifsk.rxcreatevnetroot">RxCreateVNetRoot</a>
</dt>
<dt>
<a href="ifsk.rxdereference">RxDereference</a>
</dt>
<dt>
<a href="ifsk.rxfinalizeconnection">RxFinalizeConnection</a>
</dt>
<dt>
<a href="ifsk.rxfinalizenetfcb">RxFinalizeNetFcb</a>
</dt>
<dt>
<a href="ifsk.rxfinalizenetfobx">RxFinalizeNetFobx</a>
</dt>
<dt>
<a href="ifsk.rxfinalizenetroot">RxFinalizeNetRoot</a>
</dt>
<dt>
<a href="ifsk.rxfinalizesrvcall">RxFinalizeSrvCall</a>
</dt>
<dt>
<a href="ifsk.rxfinalizesrvopen">RxFinalizeSrvOpen</a>
</dt>
<dt>
<a href="ifsk.rxfinalizevnetroot">RxFinalizeVNetRoot</a>
</dt>
<dt>
<a href="ifsk.rxfinishfcbinitialization">RxFinishFcbInitialization</a>
</dt>
<dt>
<a href="ifsk.rxforcefinalizeallvnetroots">RxForceFinalizeAllVNetRoots</a>
</dt>
<dt>
<a href="ifsk.rxreference">RxReference</a>
</dt>
<dt>
<a href="ifsk.rxsetsrvcalldomainname">RxSetSrvCallDomainName</a>
</dt>
<dt>
<a href="ifsk.rxpdereferencenetfcb">RxpDereferenceNetFcb</a>
</dt>
<dt>
<a href="ifsk.rxpreferencenetfcb">RxpReferenceNetFcb</a>
</dt>
<dt>
<a href="ifsk.the_srv_call_structure">The SRV_CALL Structure</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateNetRoot function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
