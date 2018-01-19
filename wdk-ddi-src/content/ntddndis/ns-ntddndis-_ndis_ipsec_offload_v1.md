---
UID : NS:ntddndis._NDIS_IPSEC_OFFLOAD_V1
title : _NDIS_IPSEC_OFFLOAD_V1
author : windows-driver-content
description : The NDIS_IPSEC_OFFLOAD_V1 structure provides Internet protocol security (IPsec) task offload information in the NDIS_OFFLOAD structure.Note  NDIS_IPSEC_OFFLOAD_V1 is only for NDIS 6.0.
old-location : netvista\ndis_ipsec_offload_v1.htm
old-project : netvista
ms.assetid : 8ec0a052-2327-41e5-a9fa-83bcac9566f7
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_IPSEC_OFFLOAD_V1, *PNDIS_IPSEC_OFFLOAD_V1, NDIS_IPSEC_OFFLOAD_V1
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_IPSEC_OFFLOAD_V1
req.alt-loc : ntddndis.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PNDIS_IPSEC_OFFLOAD_V1, NDIS_IPSEC_OFFLOAD_V1"
---

# _NDIS_IPSEC_OFFLOAD_V1 structure
The <b>NDIS_IPSEC_OFFLOAD_V1</b> structure provides Internet protocol security (IPsec) task offload
  information in the 
  <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure.

## Syntax
````
typedef struct _NDIS_IPSEC_OFFLOAD_V1 {
  struct {
    ULONG Encapsulation;
    ULONG AhEspCombined;
    ULONG TransportTunnelCombined;
    ULONG IPv4Options;
    ULONG Flags;
  } Supported;
  struct {
    ULONG Md5  :2;
    ULONG Sha_1  :2;
    ULONG Transport  :2;
    ULONG Tunnel  :2;
    ULONG Send  :2;
    ULONG Receive  :2;
  } IPv4AH;
  struct {
    ULONG Des  :2;
    ULONG Reserved  :2;
    ULONG TripleDes  :2;
    ULONG NullEsp  :2;
    ULONG Transport  :2;
    ULONG Tunnel  :2;
    ULONG Send  :2;
    ULONG Receive  :2;
  } IPv4ESP;
} NDIS_IPSEC_OFFLOAD_V1, *PNDIS_IPSEC_OFFLOAD_V1;
````

## Members

        
            `IPv4AH`

            A structure within NDIS_IPSEC_OFFLOAD_V1 that specifies support for AH payloads and that contains
     the following information:
        
            `IPv4ESP`

            A structure within NDIS_IPSEC_OFFLOAD_V1 that specifies support for ESP payloads and that contains
     the following information:
        
            `Supported`

            A structure within NDIS_IPSEC_OFFLOAD_V1 that specifies support for IPsec task offload and that
     contains the following information:

    ## Remarks
        The <b>NDIS_IPSEC_OFFLOAD_V1</b> structure is used in the 
    <b>IPsecV1</b> member of the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure. The
    NDIS_IPSEC_OFFLOAD_V1 structure specifies the current or supported services that a miniport adapter
    provides for Internet protocol security (IPsec).


<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> is used in the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a> structure, 
    <a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">
    NDIS_FILTER_ATTACH_PARAMETERS</a> structure, 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> OID, and the 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

For 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>,
    the <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure specifies the task offload capabilities that a miniport adapter supports. If
    the current offloads capabilities change, a miniport driver reports the new capabilities in an 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication.

The 
    <b>Encapsulation</b> member of <b>NDIS_IPSEC_OFFLOAD_V1</b> defines the IPsec offload encapsulation settings for
    the miniport adapter.

In response to an 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">
    OID_TCP_OFFLOAD_CURRENT_CONFIG</a> query request, NDIS provides a bitwise OR of the encapsulation
    flags, which indicate the supported encapsulation settings, in the 
    <b>Encapsulation</b> member. Miniport drivers must provide Ethernet encapsulation
    (NDIS_ENCAPSULATION_IEEE_802_3). The other types of encapsulation are optional.

For an 
    <a href="netvista.ndis_status_task_offload_current_config">
    NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a> status indication, the miniport driver provides a bitwise
    OR of the encapsulation flags, which indicate the current capabilities, in the 
    <b>Encapsulation</b> member.

The following flags are defined for the 
    <b>Encapsulation</b> member:



Specifies that no encapsulation offload is supported.

Specifies NULL encapsulation.

Specifies IEEE 802.3 encapsulation.

Specifies IEEE 802.3p and IEEE 802.3q encapsulation.

Specifies that IEEE 802.3p and IEEE 802.3q encapsulation settings are specified in the 
      <b>NetBufferListInfo</b> member of each 
      <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.

Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC
      1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ndis\ns-ndis-_ndis_bind_parameters.md">NDIS_BIND_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_filter_attach_parameters.md">NDIS_FILTER_ATTACH_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_ipsec_offload_v2.md">NDIS_IPSEC_OFFLOAD_V2</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_offload_attributes.md">
   NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndis_status_task_offload_current_config">
   NDIS_STATUS_TASK_OFFLOAD_CURRENT_CONFIG</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-offload-current-config">OID_TCP_OFFLOAD_CURRENT_CONFIG</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_IPSEC_OFFLOAD_V1 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>