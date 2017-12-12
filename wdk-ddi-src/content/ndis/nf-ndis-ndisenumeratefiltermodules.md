---
UID: NF.ndis.NdisEnumerateFilterModules
title: NdisEnumerateFilterModules function
author: windows-driver-content
description: The NdisEnumerateFilterModules function enumerates all the filters modules and filter intermediate driver instances in a filter stack.
old-location: netvista\ndisenumeratefiltermodules.htm
old-project: netvista
ms.assetid: cab7609e-cf87-46f6-af23-891e19ef1b80
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisEnumerateFilterModules
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisEnumerateFilterModules
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Filter_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NdisEnumerateFilterModules function



## -description
The 
  <b>NdisEnumerateFilterModules</b> function enumerates all the filters modules and filter intermediate driver
  instances in a filter stack.



## -syntax

````
NDIS_STATUS NdisEnumerateFilterModules(
  _In_    NDIS_HANDLE NdisHandle,
  _In_    PVOID       InterfaceBuffer,
  _In_    ULONG       InterfaceBufferLength,
  _Inout_ PULONG      BytesNeeded,
  _Inout_ PULONG      BytesWritten
);
````


## -parameters

### -param NdisHandle [in]

An NDIS handle that was obtained during caller initialization. For more information about this
     handle, see 
     <a href="netvista.obtaining_pool_handles">Obtaining Pool Handles</a>.
     

If the handle is an NDIS miniport adapter handle, NDIS returns information about all the interface
     modules that are currently attached to the miniport adapter, starting with the top-most filter
     module.

If the handle is an NDIS binding handle, NDIS returns information about all the filter modules that
     are currently attached to the underlying miniport adapter, starting with the top-most filter module.

If the handle is an NDIS filter module handle, NDIS returns information about all the filter modules
     that are currently attached to the underlying miniport adapter to which the specified filter module is
     attached, starting with the top-most filter module.


### -param InterfaceBuffer [in]

A pointer to a caller-allocated memory block in which NDIS returns the information for all the
     filter modules in a filter stack, starting with top-most filter. This buffer contains an 
     <a href="netvista.ndis_enum_filters">NDIS_ENUM_FILTERS</a> structure that is
     followed by zero or more 
     <a href="netvista.ndis_filter_interface">NDIS_FILTER_INTERFACE</a> structures, one
     for each filter module in the stack.


### -param InterfaceBufferLength [in]

The length, in bytes, of the caller-supplied memory block at the 
     <b>InterfaceBuffer</b> member.


### -param BytesNeeded [in, out]

A pointer to a caller-supplied variable where NDIS writes the total number of bytes that NDIS
     requires to successfully return the interface information for all the filters in the filter
     stack.


### -param BytesWritten [in, out]

A pointer to a caller-supplied variable where NDIS writes the total bytes that NDIS wrote in the
     memory at 
     <b>InterfaceBuffer</b>.


## -returns
<b>NdisEnumerateFilterModules</b> returns one of the following status values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_INVALID_PARAMETER</b></dt>
</dl><b>NdisEnumerateFilterModules</b> failed because the 
       <i>NdisHandle</i> parameter was not a valid NDIS miniport adapter, protocol binding, or filter module
       handle.
<dl>
<dt><b>NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl><b>NdisEnumerateFilterModules</b> failed because the buffer that was supplied at the 
       <i>InterfaceBuffer</i> parameter was too short for NDIS to return all the information. If a partial
       result was written at 
       <i>InterfaceBuffer</i>, the value at the 
       <i>BytesWritten</i> parameter contains the length of the partial results.

 


## -remarks
An NDIS miniport driver, protocol driver, or filter driver can call the 
    <b>NdisEnumerateFilterModules</b> function to enumerate all the filters in a filter stack.

<b>NdisEnumerateFilterModules</b> returns the list of filter modules and filter intermediate drivers from
    the top to the bottom of the driver stack. For example, if filter modules (F1 and F2) are attached to
    miniport adapter (M1) and if F2 is above F1,
    <b>NdisEnumerateFilterModules</b> returns the list in the following order: F2, F1. If there is also a
    filter intermediate driver (M2) that is bound to M1, if M2 is above F2, and if another filter (F3) is
    attached to M2, 
    <b>NdisEnumerateFilterModules</b> returns the filter list in the following order: F3, M2, F2, F1.


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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_filter_driver_function">Irql_Filter_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_enum_filters">NDIS_ENUM_FILTERS</a>
</dt>
<dt>
<a href="netvista.ndis_filter_interface">NDIS_FILTER_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisEnumerateFilterModules function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
