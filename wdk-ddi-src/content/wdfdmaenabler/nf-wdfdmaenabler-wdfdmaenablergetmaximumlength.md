---
UID: NF.wdfdmaenabler.WdfDmaEnablerGetMaximumLength
title: WdfDmaEnablerGetMaximumLength function
author: windows-driver-content
description: The WdfDmaEnablerGetMaximumLength method returns the maximum transfer length, for a single DMA transfer, that a device supports.
old-location: wdf\wdfdmaenablergetmaximumlength.htm
old-project: wdf
ms.assetid: f37359b9-807e-43dc-a66b-7b32c0921f06
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfDmaEnablerGetMaximumLength
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDmaEnablerGetMaximumLength
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDmaEnablerGetMaximumLength function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaEnablerGetMaximumLength</b> method returns the maximum transfer length, for a single <a href="wdf.dma_transactions_and_dma_transfers">DMA transfer</a>, that a device supports. 



## -syntax

````
size_t WdfDmaEnablerGetMaximumLength(
  _In_ WDFDMAENABLER DmaEnabler
);
````


## -parameters

### -param DmaEnabler [in]

A handle to a DMA enabler object that the driver obtained from a previous call to <a href="wdf.wdfdmaenablercreate">WdfDmaEnablerCreate</a>. 


## -returns
<b>WdfDmaEnablerGetMaximumLength</b> returns the maximum length of a DMA transfer, in bytes. This length is the same value that was specified in a previous call to <a href="wdf.wdfdmaenablercreate">WdfDmaEnablerCreate</a>. 

A bug check occurs if the driver supplies an invalid object handle.



The following code example obtains the maximum transfer length that a device supports for a DMA transfer.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdmaenabler.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>
</dt>
<dt>
<a href="wdf.wdfdmaenablercreate">WdfDmaEnablerCreate</a>
</dt>
<dt>
<a href="wdf.wdfdmaenablergetfragmentlength">WdfDmaEnablerGetFragmentLength</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerGetMaximumLength method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
