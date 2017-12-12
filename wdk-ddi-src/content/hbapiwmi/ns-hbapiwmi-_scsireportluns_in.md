---
UID: NS.HBAPIWMI._SCSIREPORTLUNS_IN
title: _ScsiReportLuns_IN
author: windows-driver-content
description: The ScsiReportLuns_IN structure is used to deliver input parameter data to the ScsiReportLuns WMI method.
old-location: storage\scsireportluns_in2.htm
old-project: storage
ms.assetid: 6de38cf4-a543-4cc9-aa6f-1804fc858040
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _ScsiReportLuns_IN, ScsiReportLuns_IN, *PScsiReportLuns_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ScsiReportLuns_IN
req.alt-loc: Hbapiwmi.h
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
---

# _ScsiReportLuns_IN structure



## -description
The ScsiReportLuns_IN structure is used to deliver input parameter data to the <a href="storage.scsireportluns">ScsiReportLuns</a> WMI method. 



## -syntax

````
typedef struct _ScsiReportLuns_IN {
  UCHAR     Cdb[12];
  UCHAR     HbaPortWWN[8];
  UCHAR     DiscoveredPortWWN[8];
  ULONGLONG FcLun;
} ScsiReportLuns_IN, *PScsiReportLuns_IN;
````


## -struct-fields

### -field Cdb

Contains the command descriptor block that holds the SCSI report LUNs command to be sent to the target device. 


### -field HbaPortWWN

Contains a worldwise name for the HBA through which the target is accessed. 


### -field DiscoveredPortWWN

Contains a worldwide name for the port through which the target device is accessed. 


### -field FcLun

Indicates the logical unit number of the logical unit that will receive the SCSI report luns command.


## -remarks
The WMI tool suite generates a declaration of the ScsiReportLuns_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbaadaptermethods_wmi_class">MSFC_HBAAdapterMethods WMI Class</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsireportluns">ScsiReportLuns</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ScsiReportLuns_IN structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
