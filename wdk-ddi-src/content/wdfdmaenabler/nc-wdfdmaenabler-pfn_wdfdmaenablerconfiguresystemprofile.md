---
UID: NC:wdfdmaenabler.PFN_WDFDMAENABLERCONFIGURESYSTEMPROFILE
title: PFN_WDFDMAENABLERCONFIGURESYSTEMPROFILE function
author: windows-driver-content
description: The WdfDmaEnablerConfigureSystemProfile method configures the hardware-specific settings for a system-mode DMA enabler and completes the resource initialization.
old-location: wdf\wdfdmaenablerconfiguresystemprofile.htm
old-project: wdf
ms.assetid: 3374EBB8-F43A-4A2A-92AC-623B39F5EFA0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDMAENABLERCONFIGURESYSTEMPROFILE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WdfDmaEnablerConfigureSystemProfile
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS
req.product: Windows 10 or later.
---

# PFN_WDFDMAENABLERCONFIGURESYSTEMPROFILE function



## -description
<p class="CCE_Message">[Applies to KMDF only]


   The <b>WdfDmaEnablerConfigureSystemProfile</b> method 
  configures the hardware-specific settings for a system-mode DMA enabler and completes the resource initialization.



## -syntax

````
NTSTATUS WdfDmaEnablerConfigureSystemProfile(
  _In_ WDFDMAENABLER                  DmaEnabler,
  _In_ PWDF_DMA_SYSTEM_PROFILE_CONFIG ProfileConfig,
  _In_ WDF_DMA_DIRECTION              ConfigDirection
);
````


## -parameters

### -param DmaEnabler [in]

A handle to a DMA enabler object.


### -param ProfileConfig [in]

A pointer to a <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_system_profile_config.md">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure. Drivers must initialize this structure by calling <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdf_dma_system_profile_config_init.md">WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</a>.


### -param ConfigDirection [in]

A <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_direction.md">WDF_DMA_DIRECTION</a>-typed value that specifies the direction of the DMA transfer operation. If the <a href="..\wdfdmaenabler\ne-wdfdmaenabler-_wdf_dma_profile.md">WDF_DMA_PROFILE</a> value for this enabler is not <b>WdfDmaProfileSystemDuplex</b>, the framework ignores this parameter.


## -returns
<b>WdfDmaEnablerConfigureSystemProfile</b> returns STATUS_SUCCESS if the operation succeeds.  Otherwise, the method might return one of the following values.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The driver requested a DMA configuration that is not supported on the current operating system.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The driver supplied NULL in the <i>ProfileConfig</i> parameter.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The <b>Size</b> member of the structure pointed to by the <i>ProfileConfig</i> parameter is not equal to the size of the <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_system_profile_config.md">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <b>DmaDescriptor</b> member of the structure pointed to by the <i>ProfileConfig</i> parameter is NULL or the <i>ConfigDirection</i> parameter contains an invalid value.

 


## -remarks
Before calling <b>WdfDmaEnablerConfigureSystemProfile</b>, the driver must call <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a> to create the enabler object.

A driver typically calls <b>WdfDmaEnablerConfigureSystemProfile</b> from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function.

If your driver specified a duplex profile when it called <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>, the <b>WdfDmaEnablerConfigureSystemProfile</b> method's <i>ConfigDirection</i> parameter's value must be <b>WdfDmaDirectionReadFromDevice</b> to obtain the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure for read operations and <b>WdfDmaDirectionWriteToDevice</b> to obtain the <b>DMA_ADAPTER</b> structure for write operations.

If the DMA enabler is a duplex enabler, the driver must initialize a particular direction before it can use it.  

 If your driver did not specify a duplex profile, the driver can specify either <b>WdfDmaDirectionReadFromDevice</b> or <b>WdfDmaDirectionWriteToDevice</b>.
 

The following code example is from a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. This example initializes a <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_system_profile_config.md">WDF_DMA_SYSTEM_PROFILE_CONFIG</a> structure and calls <b>WdfDmaEnablerConfigureSystemProfile</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdf_dma_enabler_config_init.md">WDF_DMA_ENABLER_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdf_dma_system_profile_config_init.md">WDF_DMA_SYSTEM_PROFILE_CONFIG_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaEnablerConfigureSystemProfile method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
