---
UID: NS.WDM._REG_QUERY_KEY_INFORMATION
title: _REG_QUERY_KEY_INFORMATION
author: windows-driver-content
description: The REG_QUERY_KEY_INFORMATION structure describes the metadata that is about to be queried for a key.
old-location: kernel\reg_query_key_information.htm
old-project: kernel
ms.assetid: 88c64e9a-dbf2-4feb-9ce2-615b5ba98439
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _REG_QUERY_KEY_INFORMATION, REG_QUERY_KEY_INFORMATION, *PREG_QUERY_KEY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows XP and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_QUERY_KEY_INFORMATION
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _REG_QUERY_KEY_INFORMATION structure



## -description
The <b>REG_QUERY_KEY_INFORMATION</b> structure describes the metadata that is about to be queried for a key.



## -syntax

````
typedef struct _REG_QUERY_KEY_INFORMATION {
  PVOID                 Object;
  KEY_INFORMATION_CLASS KeyInformationClass;
  PVOID                 KeyInformation;
  ULONG                 Length;
  PULONG                ResultLength;
  PVOID                 CallContext;
  PVOID                 ObjectContext;
  PVOID                 Reserved;
} REG_QUERY_KEY_INFORMATION, *PREG_QUERY_KEY_INFORMATION;
````


## -struct-fields

### -field Object

A pointer to the registry key object for the key whose metadata is about to be queried.


### -field KeyInformationClass

The <a href="kernel.key_information_class">KEY_INFORMATION_CLASS</a> value that indicates the type of information to be returned by the system.


### -field KeyInformation

A pointer to a buffer that contains the information to be returned by the system. The format of the buffer depends on the value of <b>KeyInformationClass</b>. For more information see <a href="kernel.key_information_class">KEY_INFORMATION_CLASS</a>.


### -field Length

Specifies the size, in bytes, of the <b>KeyInformation</b> buffer.


### -field ResultLength

Pointer to a variable that receives (from the system) the amount of valid data, in bytes, in the <b>KeyInformation</b> buffer.


### -field CallContext

Optional driver-defined context information that the driver's <a href="kernel.registrycallback">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="kernel.cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system. 


## -remarks
The system passes this structure to the <a href="kernel.registrycallback">RegistryCallback</a> routine every time a thread attempts to query the metadata for a key—for example, when a user-mode thread calls <b>RegQueryInfoKey</b> or when a driver calls <a href="kernel.zwquerykey">ZwQueryKey</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available on Microsoft Windows XP and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.cmsetcallbackobjectcontext">CmSetCallbackObjectContext</a>
</dt>
<dt>
<a href="kernel.registrycallback">RegistryCallback</a>
</dt>
<dt>
<a href="kernel.zwquerykey">ZwQueryKey</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_QUERY_KEY_INFORMATION structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
