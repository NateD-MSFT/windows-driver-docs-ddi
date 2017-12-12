---
UID: NS.WINDOT11._DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS
title: _DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS
author: windows-driver-content
description: The parameters for a received invitation response are specified in a DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS structure. This structure is sent with an NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_RESPONSE indication.
old-location: netvista\_dot11_received_invitation_response_parameters.htm
old-project: netvista
ms.assetid: 9DAFC0E0-A3F9-4EF1-8FD1-3213AA1CBD18
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS, *PDOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS, DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS
req.alt-loc: Windot11.h
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
req.product: Windows 10 or later.
---

# _DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS structure



## -description

## -syntax

````
typedef struct _DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  TransmitterDeviceAddress;
  DOT11_MAC_ADDRESS  BSSID;
  DOT11_DIALOG_TOKEN DialogToken;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS, *PDOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS;
````


## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following:

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_RECEIVED_INVITATION_RESPONSE_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field TransmitterDeviceAddress

The address of the device that transmitted the invitaion response packet.


### -field BSSID

The BSSID in the received invitation response packet.


### -field DialogToken

The dialog token received in invitation response packet.


### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) received in the the invitation response packet. This offset is from the start of the buffer that contains this structure.


### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista._dot11_received_invitation_response_parameters">DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_RECEIVED_INVITATION_RESPONSE_PARAMETERS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
