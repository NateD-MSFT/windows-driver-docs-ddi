---
UID: NS:wdm._FILE_MEMORY_PARTITION_INFORMATION
title: "_FILE_MEMORY_PARTITION_INFORMATION"
author: windows-driver-content
description: Stores information about memory partition. This structure is used by the ZwSetInformationFile function.
old-location: ifsk\_file_memory_partition_information.htm
old-project: ifsk
ms.assetid: 1d74aec3-dbc5-4494-ba52-135e3f545c1b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFILE_MEMORY_PARTITION_INFORMATION, FILE_MEMORY_PARTITION_INFORMATION, FILE_MEMORY_PARTITION_INFORMATION structure [Kernel-Mode Driver Architecture], _FILE_MEMORY_PARTITION_INFORMATION, ifsk._file_memory_partition_information, wdm/FILE_MEMORY_PARTITION_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	FILE_MEMORY_PARTITION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: FILE_MEMORY_PARTITION_INFORMATION, *PFILE_MEMORY_PARTITION_INFORMATION
req.product: Windows 10 or later.
---

# _FILE_MEMORY_PARTITION_INFORMATION structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Stores information about memory partition. This structure is used by the <b>ZwSetInformationFile</b> function.


## -struct-fields




### -field OwnerPartitionHandle

Handle to the specified partition.


### -field Flags



#### AllFlags

Bitwise of all flags. 


### -field Flags.DUMMYSTRUCTNAME


### -field Flags.DUMMYSTRUCTNAME.NoCrossPartitionAccess

Determines whether cross-partition access is allowed.


### -field Flags.DUMMYSTRUCTNAME.Spare

 



