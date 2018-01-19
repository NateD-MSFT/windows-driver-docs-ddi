---
UID : NS:ntddndis._NDIS_SWITCH_NIC_PARAMETERS
title : _NDIS_SWITCH_NIC_PARAMETERS
author : windows-driver-content
description : The NDIS_SWITCH_NIC_PARAMETERS structure specifies the configuration parameters for a network adapter (NIC) that is connected to a Hyper-V extensible switch port.
old-location : netvista\ndis_switch_nic_parameters.htm
old-project : netvista
ms.assetid : 52B9DD8B-E96F-464C-9D98-5EF8B6C050C5
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_SWITCH_NIC_PARAMETERS, *PNDIS_SWITCH_NIC_PARAMETERS, NDIS_SWITCH_NIC_PARAMETERS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h, Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_SWITCH_NIC_PARAMETERS
req.alt-loc : Ntddndis.h
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
req.typenames : "*PNDIS_SWITCH_NIC_PARAMETERS, NDIS_SWITCH_NIC_PARAMETERS"
---

# _NDIS_SWITCH_NIC_PARAMETERS structure
The <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure specifies the configuration parameters for a network adapter (NIC) that is connected to a Hyper-V extensible switch port.  



The <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure specifies the configuration parameters for a network adapter (NIC) that is connected to a Hyper-V extensible switch port.

## Syntax
````
typedef struct _NDIS_SWITCH_NIC_PARAMETERS {
  NDIS_OBJECT_HEADER           Header;
  ULONG                        Flags;
  NDIS_SWITCH_NIC_NAME         NicName;
  NDIS_SWITCH_NIC_FRIENDLYNAME NicFriendlyName;
  NDIS_SWITCH_PORT_ID          PortId;
  NDIS_SWITCH_NIC_INDEX        NicIndex;
  NDIS_SWITCH_NIC_TYPE         NicType;
  NDIS_SWITCH_NIC_STATE        NicState;
  NDIS_VM_NAME                 VmName;
  NDIS_VM_FRIENDLYNAME         VMFriendlyName;
  GUID                         NetCfgInstanceId;
  ULONG                        MTU;
  USHORT                       NumaNodeId;
  UCHAR                        PermanentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  UCHAR                        VMMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  UCHAR                        CurrentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  BOOLEAN                      VFAssigned;
} NDIS_SWITCH_NIC_PARAMETERS, *PNDIS_SWITCH_NIC_PARAMETERS;
````

## Members

        
            `CurrentMacAddress`

            A <b>UCHAR</b> array that specifies the MAC address that is currently being used in the switch for the network adapter. If <i>AllowMacSpoofing</i> and <i>AllowTeaming</i> are both FALSE, then this value will be equal to <i>PermanentMacAddress</i>. If <i>AllowMacSpoofing</i> is TRUE, this value will be equal to the <i>VMMacAddress</i>. If <i>AllowTeaming</i> is TRUE and teaming failover has occurred inside the VM, the <i>CurrentMacAddress</i> will be equal to the MAC address that was failed over to the network adapter or <i>PermanentMacAddress</i> if no failover has occurred.
        
            `Flags`

            A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. The following flag value is defined.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
        
            `Header`

            The type, revision, and size of the <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The <b>Type</b> member of <b>Header</b> must be set to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure, the <b>Revision</b> member of <b>Header</b> must be set to the following value:
        
            `MTU`

            A <b>ULONG</b> value that specifies the maximum transmission unit (MTU) size, in bytes, for the network adapter.

<div class="alert"><b>Note</b>  The value of this member can change during the lifetime of a VM NIC. Therefore, extensions should read this member of the <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure that is passed down with the following OIDs:<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598262">OID_SWITCH_NIC_CONNECT</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh846216">OID_SWITCH_NIC_UPDATED</a>
</li>
</ul>
</div>
<div> </div>
        
            `NetCfgInstanceId`

            A GUID value that specifies the <b>NetCfgInstanceId</b> registry value of the
underlying network adapter.

<div class="alert"><b>Note</b>  This member is valid only if the <b>NicType</b> member is set to <b>NdisSwitchNicTypeExternal</b> or <b>NdisSwitchNicTypeInternal</b>.  <b>NetCfgInstanceId</b> will not be valid until after the virtual network adapter has been initialized.</div>
<div> </div>
        
            `NicFriendlyName`

            An NDIS_SWITCH_NIC_FRIENDLYNAME value that specifies the user-friendly description of the network adapter.
        
            `NicIndex`

            An NDIS_SWITCH_NIC_INDEX value that specifies the index of the network adapter that is connected to the  extensible switch port specified by the <b>PortId</b> member.

For more information on NDIS_SWITCH_NIC_INDEX values, see <a href="https://msdn.microsoft.com/969333DA-0282-474B-8D56-72CD623C5329">Network Adapter Index Values</a>.
        
            `NicName`

            An NDIS_SWITCH_NIC_NAME value that specifies the unique internal name of the network adapter that is connected to an extensible switch port. 

For more information, see the Remarks section.
        
            `NicState`

            An <a href="..\ntddndis\ne-ntddndis-_ndis_switch_nic_state.md">NDIS_SWITCH_NIC_STATE</a> value that specifies the current state of the network adapter.
        
            `NicType`

            An <a href="..\ntddndis\ne-ntddndis-_ndis_switch_nic_type.md">NDIS_SWITCH_NIC_TYPE</a> value that specifies the type of the network adapter that is connected to an extensible switch port.
        
            `NumaNodeId`

            A <b>USHORT</b> value that specifies the identifier for the preferred Non-Uniform Memory Access (NUMA) node of a CPU. On computers that support NUMA architecture, the preferred NUMA node is the CPU that has the smallest distance to the network adapter.



<div class="alert"><b>Note</b>  This member is valid only if the <b>NicType</b> member is set to <b>NdisSwitchNicTypeSynthetic</b> or <b>NdisSwitchNicTypeEmulated</b>.</div>
<div> </div>
        
            `PermanentMacAddress`

            A <b>UCHAR</b> array that specifies the media access control (MAC) address as configured on the host partition for  the network adapter. This can be different from the MAC address currently in use by the network adapter.
        
            `PortId`

            An NDIS_SWITCH_PORT_ID value that contains the unique identifier of the extensible switch port to which the network adapter is connected.
        
            `VFAssigned`

            A <b>BOOLEAN</b> value that, if set to <b>TRUE</b>, specifies that the network adapter is attached to a PCI Express (PCIe) virtual function (VF). A VF is exposed by an underlying physical network adapter that supports the single root I/O virtualization (SR-IOV) interface.

For more information, see the Remarks section.

<div class="alert"><b>Note</b>  The <b>VFAssigned</b> member is valid only if the <b>NicType</b> member contains a value of <b>NdisSwitchNicTypeEmulated</b> or <b>NdisSwitchNicTypeSynthetic</b>. This member must be set to <b>FALSE</b> if the <b>NicType</b> member contains a value of <b>NdisSwitchNicTypeExternal</b> or <b>NdisSwitchNicTypeInternal</b>.</div>
<div> </div>
        
            `VMMacAddress`

            A <b>UCHAR</b> array that specifies the MAC address that is configured on the network adapter inside the VM itself. The field is all zeros for non VM NICs. If <i>AllowMacSpoofing</i> (from <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_property_security.md">NDIS_SWITCH_PORT_PROPERTY_SECURITY</a>) is TRUE, this address will also be applied to the <i>CurrentMacAddress.</i>
        
            `VmName`

            An NDIS_VM_NAME value that specifies the unique internal name of the Hyper-V child partition in which the guest operating system that exposes the network adapter is running.



The Hyper-V child partition is also known as a virtual machine (VM).

<div class="alert"><b>Note</b>  This member is valid only if the <b>NicType</b> member contains a value of <b>NdisSwitchNicSyntheticNic</b> or <b>NdisSwitchNicEmulatedNic.</b></div>
<div> </div>

    ## Remarks
        OID query requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh598261">OID_SWITCH_NIC_ARRAY</a> return an <a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_array.md">NDIS_SWITCH_NIC_ARRAY</a> structure that contains zero or more elements. Each element is formatted as an <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure.

The <b>NDIS_SWITCH_NIC_PARAMETERS</b> structure is also used in the following OID requests: 


<a href="https://msdn.microsoft.com/library/windows/hardware/hh598263">OID_SWITCH_NIC_CREATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598262">OID_SWITCH_NIC_CONNECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh846216">OID_SWITCH_NIC_UPDATED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh598265">OID_SWITCH_NIC_DISCONNECT</a>


 Based on the value <b>NicType</b> member, the format of the <b>NicName</b> member is as follows:

If the <b>NicType</b> member is set to <b>NdisSwitchNicTypeExternal</b>, the value of the <b>NicName</b> member is the unique instance identifier (<b>InstanceId</b>) of the physical network adapter that is bound to the external network adapter. This type of  network adapter is exposed in the management operating system that runs in the Hyper-V parent partition.


The external network adapter provides a connection to the  physical network interface that is available on the host. The external network adapter can be accessed by the Hyper-V parent partition and all child partitions.

If the <b>NicType</b> member is set to <b>NdisSwitchNicTypeInternal</b>, the value of the <b>NicName</b> member is the device display name that identifies the internal  network adapter. This type of network adapter is exposed in the management operating system of a Hyper-V parent partition.


The internal network adapter can be accessed by the Hyper-V parent partition and all child partitions. However, the internal network adapter does not connect to the physical network interface that is available on the host.

For all other <b>NicType</b> member values, the value of the <b>NicName</b> member is uniquely assigned to the synthetic or emulated network adapter by the policy management interface.
These types of network adapters are exposed in the guest operating system that runs is a Hyper-V child partition.

A PCIe VF is created and allocated by an underlying physical adapter that supports the SR-IOV interface. After the PCIe VF is created, the virtualization stack attaches, or <i>assigns</i>,  a Hyper-V child partition to the VF. The guest operating system that runs in this partition exposes a virtual machine (VM) network adapter that is attached, or <i>assigned</i> to the underlying SR-IOV physical adapter.

If the <b>VFAssigned</b> member is set to <b>TRUE</b>, packets are routed directly between the underlying SR-IOV physical network adapter and the virtual adapter. However, because the extensible switch is not involved in packet delivery, extensible switch port policies, such as access control lists (ACLs), are not applied to these packets.

The extension can remove a VF assignment by issuing an <a href="https://msdn.microsoft.com/library/windows/hardware/hh598206">NDIS_STATUS_SWITCH_PORT_REMOVE_VF</a> status indication. This indication causes the packets to be delivered through an extensible switch port instead of directly between the VM network adapter and the SR-IOV physical adapter. This allows the extensible switch port policies to be applied to packets that are received or sent over the extensible switch port. When the extension makes the <b>NDIS_STATUS_SWITCH_PORT_REMOVE_VF</b> status indication, it specifies which extensible switch port the virtual network adapter is connected to.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh598206">NDIS_STATUS_SWITCH_PORT_REMOVE_VF</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h, Fwpsk.h) |

    ## See Also

        <dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_array.md">NDIS_SWITCH_NIC_ARRAY</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_switch_nic_parameters.md">NDIS_SWITCH_NIC_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddndis\ne-ntddndis-_ndis_switch_nic_state.md">NDIS_SWITCH_NIC_STATE</a>
</dt>
<dt>
<a href="..\ntddndis\ne-ntddndis-_ndis_switch_nic_type.md">NDIS_SWITCH_NIC_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598206">NDIS_STATUS_SWITCH_PORT_REMOVE_VF</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598261">OID_SWITCH_NIC_ARRAY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598262">OID_SWITCH_NIC_CONNECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598263">OID_SWITCH_NIC_CREATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598264">OID_SWITCH_NIC_DELETE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598265">OID_SWITCH_NIC_DISCONNECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598268">OID_SWITCH_NIC_SAVE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh598269">OID_SWITCH_NIC_SAVE_COMPLETE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh846216">OID_SWITCH_NIC_UPDATED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_NIC_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>