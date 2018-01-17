---
UID: NC:wdffdo.PFN_WDFFDOGETDEFAULTCHILDLIST
title: PFN_WDFFDOGETDEFAULTCHILDLIST function
author: windows-driver-content
description: The WdfFdoGetDefaultChildList method returns a handle to a specified device's default child list.
old-location: wdf\wdffdogetdefaultchildlist.htm
old-project: wdf
ms.assetid: b90c82ad-0531-4564-b30d-48e980282e85
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFFDOGETDEFAULTCHILDLIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfFdoGetDefaultChildList
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
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# PFN_WDFFDOGETDEFAULTCHILDLIST function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoGetDefaultChildList</b> method returns a handle to a specified device's default child list.



## -syntax

````
WDFCHILDLIST WdfFdoGetDefaultChildList(
  _In_ WDFDEVICE Fdo
);
````


## -parameters

### -param Fdo [in]

A handle to a framework device object.


## -returns
If the operation succeeds, <b>WdfFdoGetDefaultChildList</b> returns a handle to the default child list that is associated with the device that is specified by <i>Fdo</i>. Otherwise the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.


## -remarks
Before calling <b>WdfFdoGetDefaultChildList</b>, your driver must call <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> to configure the default child list. Otherwise, <b>WdfFdoGetDefaultChildList</b> returns <b>NULL</b>.

For more information about child lists, see <a href="https://msdn.microsoft.com/6e46b456-7d2d-4c6e-8692-7f310366387d">Dynamic Enumeration</a>.

The following code example obtains a handle to a device's default child list.


## -see-also
<dl>
<dt>
<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoGetDefaultChildList method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
