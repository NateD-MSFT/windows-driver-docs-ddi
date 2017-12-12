---
UID: NS.WINSPLP._MONITOREX
title: _MONITOREX
author: windows-driver-content
description: The MONITOREX structure is obsolete and supported for compatibility purposes only.
old-location: print\monitorex.htm
old-project: print
ms.assetid: f03f72a8-8dc1-4e27-b89b-1afea16a177a
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: _MONITOREX, *LPMONITOREX, MONITOREX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MONITOREX
req.alt-loc: winsplp.h
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
req.product: Windows 10 or later.
---

# _MONITOREX structure



## -description
The MONITOREX structure is obsolete and supported for compatibility purposes only. New print monitors should implement <a href="print.initializeprintmonitor2">InitializePrintMonitor2</a> and <a href="print.monitor2">MONITOR2</a> so that they can be used with print server clusters.

The MONITOREX structure is used as the return value for a print monitor's <a href="print.initializeprintmonitor">InitializePrintMonitor</a> function.



## -syntax

````
typedef struct _MONITOREX {
  DWORD   dwMonitorSize;
  MONITOR Monitor;
} MONITOREX, *LPMONITOREX;
````


## -struct-fields

### -field dwMonitorSize

Specifies the size, in bytes, of the Monitor <b>member</b>.


### -field Monitor

Is a <a href="print.monitor">MONITOR</a> structure.


## -remarks
Print monitors are responsible for filling in the MONITOREX and MONITOR structures.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winsplp.h (include Winsplp.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.monitor">MONITOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITOREX structure%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
