---
UID : NE:ntddcdrm._CDROM_PERFORMANCE_TOLERANCE_TYPE
title : _CDROM_PERFORMANCE_TOLERANCE_TYPE
author : windows-driver-content
description : The CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration defines the allowable tolerances for performance data. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request.
old-location : storage\cdrom_performance_tolerance_type.htm
old-project : storage
ms.assetid : 2369582F-D042-474D-9191-F9E7BDD3725E
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _CDROM_PERFORMANCE_TOLERANCE_TYPE, *PCDROM_PERFORMANCE_TOLERANCE_TYPE, CDROM_PERFORMANCE_TOLERANCE_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddcdrm.h
req.include-header : Ntddcdrm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CDROM_PERFORMANCE_TOLERANCE_TYPE
req.alt-loc : Ntddcdrm.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PCDROM_PERFORMANCE_TOLERANCE_TYPE, CDROM_PERFORMANCE_TOLERANCE_TYPE"
---

# _CDROM_PERFORMANCE_TOLERANCE_TYPE Enumeration
The <b>CDROM_PERFORMANCE_TOLERANCE_TYPE</b> enumeration defines the allowable tolerances for performance data. It is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request.

## Syntax
````
typedef enum _CDROM_PERFORMANCE_TOLERANCE_TYPE { 
   Cdrom10Nominal20Exceptions   = 1
} CDROM_PERFORMANCE_TOLERANCE_TYPE, *PCDROM_PERFORMANCE_TOLERANCE_TYPE;
````

## Constants

<table>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<dl>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a>
</dt>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PERFORMANCE_TOLERANCE_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>