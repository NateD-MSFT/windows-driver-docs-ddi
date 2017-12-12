---
UID: NS.D3DKMTHK._D3DKMT_SIGNALSYNCHRONIZATIONOBJECT
title: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT
author: windows-driver-content
description: The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the D3DKMTSignalSynchronizationObject function signals.
old-location: display\d3dkmt_signalsynchronizationobject.htm
old-project: display
ms.assetid: 13368ea2-dd2e-48af-b528-097104dffb60
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT, D3DKMT_SIGNALSYNCHRONIZATIONOBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SIGNALSYNCHRONIZATIONOBJECT
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure



## -description
The D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure contains information about the synchronization events that the <a href="display.d3dkmtsignalsynchronizationobject">D3DKMTSignalSynchronizationObject</a> function signals. 



## -syntax

````
typedef struct _D3DKMT_SIGNALSYNCHRONIZATIONOBJECT {
  D3DKMT_HANDLE        hContext;
  UINT                 ObjectCount;
  D3DKMT_HANDLE        ObjectHandleArray[D3DDDI_MAX_OBJECT_SIGNALED];
  D3DDDICB_SIGNALFLAGS Flags;
} D3DKMT_SIGNALSYNCHRONIZATIONOBJECT;
````


## -struct-fields

### -field hContext

[in] A kernel-mode handle to a context that signals the synchronization events in the array that the <b>ObjectHandleArray</b> member specifies.


### -field ObjectCount

[in] The number of synchronization events in the <b>ObjectHandleArray</b> array. 


### -field ObjectHandleArray

[in] An array of kernel-mode handles to the synchronization events that the context that is specified by the <b>hContext</b> member signals. The D3DDDI_MAX_OBJECT_SIGNALED constant, which is defined as 32, indicates the maximum number of synchronization events that the context can signal. 


### -field Flags

[in] A <a href="display.d3dddicb_signalflags">D3DDDICB_SIGNALFLAGS</a> structure that indicates, in bit-field flags, signaling behavior.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddicb_signalflags">D3DDDICB_SIGNALFLAGS</a>
</dt>
<dt>
<a href="display.d3dkmtsignalsynchronizationobject">D3DKMTSignalSynchronizationObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SIGNALSYNCHRONIZATIONOBJECT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
