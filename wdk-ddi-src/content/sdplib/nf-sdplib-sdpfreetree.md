---
UID: NF:sdplib.SdpFreeTree
title: SdpFreeTree function
author: windows-driver-content
description: The Bluetooth SdpFreeTree function is used to free the memory allocated for the tree-based representation of an SDP record.
old-location: bltooth\sdpfreetree.htm
old-project: bltooth
ms.assetid: 7d3f743e-2422-474d-aaad-4386e0dc100a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SdpFreeTree, SdpFreeTree function [Bluetooth Devices], bltooth.sdpfreetree, bth_funcs_526ed9cd-2c07-4c1f-a420-dec6fe930e44.xml, sdplib/SdpFreeTree
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sdplib.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
req.target-min-winversvr: 
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sdplib.h
api_name:
-	SdpFreeTree
product:
- Windows
targetos: Windows
req.typenames: SDCMD_DESCRIPTOR, *PSDCMD_DESCRIPTOR
req.product: Windows 10 or later.
---

# SdpFreeTree function


## -description


The Bluetooth 
  <b>SdpFreeTree</b> function is used to free the memory allocated for the tree-based representation of an SDP
  record.


## -parameters




### -param Tree [in]

The root node of the SDP tree-based representation to be freed.


## -returns



Possible return values include:




## -remarks



Callers should perform an 
    <b>SdpFreeTree</b> call when the tree-based representation of an SDP record is no longer needed. The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536818">SdpCreateNodeTree</a> and 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536794">SdpConvertStreamToTree</a> functions
    allocate the memory for the tree representations of SDP records that they create. The 
    <b>SdpFreeTree</b> function releases the memory allocated to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536851">SDP_TREE_ROOT_NODE</a> structure that these
    functions create and all 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a> structures associated with the tree
    representation.

Bluetooth profile drivers can obtain a pointer to the 
    <b>SdpFreeTree</b> function through the 
    <a href="https://msdn.microsoft.com/c9aeaaed-f017-4b23-b867-d704c4f8afb6">
    BTHDDI_SDP_NODE_INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536635">BTHDDI_SDP_NODE_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536848">SDP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536851">SDP_TREE_ROOT_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536794">SdpConvertStreamToTree</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536818">SdpCreateNodeTree</a>
 

 

