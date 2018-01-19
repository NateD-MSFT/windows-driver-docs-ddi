---
UID : NS:fltuserstructures._INSTANCE_AGGREGATE_STANDARD_INFORMATION
title : _INSTANCE_AGGREGATE_STANDARD_INFORMATION
author : windows-driver-content
description : The caller-allocated INSTANCE_AGGREGATE_STANDARD_INFORMATION structure contains information for either a minifilter driver instance or a legacy filter driver.
old-location : ifsk\instance_aggregate_standard_information.htm
old-project : ifsk
ms.assetid : 35311ee7-d023-4b04-b510-a949ab9a40ca
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _INSTANCE_AGGREGATE_STANDARD_INFORMATION, *PINSTANCE_AGGREGATE_STANDARD_INFORMATION, INSTANCE_AGGREGATE_STANDARD_INFORMATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : fltuserstructures.h
req.include-header : FltUser.h, FltKernel.h
req.target-type : Windows
req.target-min-winverclnt : This structure is available starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : INSTANCE_AGGREGATE_STANDARD_INFORMATION
req.alt-loc : fltuserstructures.h
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
req.typenames : "*PINSTANCE_AGGREGATE_STANDARD_INFORMATION, INSTANCE_AGGREGATE_STANDARD_INFORMATION"
---

# _INSTANCE_AGGREGATE_STANDARD_INFORMATION structure
The caller-allocated INSTANCE_AGGREGATE_STANDARD_INFORMATION structure contains information for either a minifilter driver instance or a legacy filter driver.

## Syntax
````
typedef struct _INSTANCE_AGGREGATE_STANDARD_INFORMATION {
  ULONG NextEntryOffset;
  ULONG Flags;
  union {
    struct {
      ULONG               Flags;
      ULONG               FrameID;
      FLT_FILESYSTEM_TYPE VolumeFileSystemType;
      USHORT              InstanceNameLength;
      USHORT              InstanceNameBufferOffset;
      USHORT              AltitudeLength;
      USHORT              AltitudeBufferOffset;
      USHORT              VolumeNameLength;
      USHORT              VolumeNameBufferOffset;
      USHORT              FilterNameLength;
      USHORT              FilterNameBufferOffset;
#if FLT_MGR_WIN8
      ULONG               SupportedFeatures;
    } MiniFilter;
#endif 
    struct {
      ULONG  Flags;
      USHORT AltitudeLength;
      USHORT AltitudeBufferOffset;
      USHORT VolumeNameLength;
      USHORT VolumeNameBufferOffset;
      USHORT FilterNameLength;
      USHORT FilterNameBufferOffset;
#if FLT_MGR_WIN8
      ULONG  SupportedFeatures;
#endif 
    } LegacyFilter;
  } Type;
} INSTANCE_AGGREGATE_STANDARD_INFORMATION, *PINSTANCE_AGGREGATE_STANDARD_INFORMATION;
````

## Members

        
            `Flags`

            Indicates whether the filter driver is a legacy filter driver or a minifilter driver.  This member must contain one of the following flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_IASI_IS_MINIFILTER

</td>
<td>
The filter driver is a minifilter driver - use the <b>MiniFilter</b> portion of the union.

</td>
</tr>
<tr>
<td>
FLTFL_IASI_IS_LEGACYFILTER

</td>
<td>
The filter driver is a legacy filter driver - use the <b>LegacyFilter</b> portion of the union.

</td>
</tr>
</table>
        
            `NextEntryOffset`

            Byte offset of the next INSTANCE_AGGREGATE_STANDARD_INFORMATION structure if multiple structures are present in a buffer. This member is zero if no other structures follow this one.
        
            `Type`

            

    ## Remarks
        A structure of type INSTANCE_AGGREGATE_STANDARD_INFORMATION can be allocated from paged or nonpaged pool.  This structure is passed as a parameter to routines such as the following:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>



<a href="..\fltkernel\nf-fltkernel-fltgetinstanceinformation.md">FltGetInstanceInformation</a>


The INSTANCE_AGGREGATE_STANDARD_INFORMATION structure must be aligned on a LONGLONG (8-byte) boundary. If a buffer contains two or more of these structures, the <b>NextEntryOffset</b> value in each entry falls on an 8-byte boundary.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltuserstructures.h (include FltUser.h, FltKernel.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540541">FilterInstanceFindFirst</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541493">FilterInstanceFindNext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541499">FilterInstanceGetInformation</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541541">FilterVolumeInstanceFindFirst</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541551">FilterVolumeInstanceFindNext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetinstanceinformation.md">FltGetInstanceInformation</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_instance_basic_information.md">INSTANCE_BASIC_INFORMATION</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_instance_full_information.md">INSTANCE_FULL_INFORMATION</a>
</dt>
<dt>
<a href="..\fltuserstructures\ns-fltuserstructures-_instance_partial_information.md">INSTANCE_PARTIAL_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20INSTANCE_AGGREGATE_STANDARD_INFORMATION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>