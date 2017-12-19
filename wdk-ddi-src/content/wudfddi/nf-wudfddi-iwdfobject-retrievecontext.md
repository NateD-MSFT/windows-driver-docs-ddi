---
UID: NF.wudfddi.IWDFObject.RetrieveContext
title: IWDFObject::RetrieveContext method
author: windows-driver-content
description: The RetrieveContext method retrieves a context that was previously registered through the IWDFObject::AssignContext method.
old-location: wdf\iwdfobject_retrievecontext.htm
old-project: wdf
ms.assetid: b76acae1-3c37-4095-bf8b-1785dc90f378
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IWDFObject, IWDFObject::RetrieveContext, RetrieveContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFObject.RetrieveContext
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.product: Windows 10 or later.
---

# IWDFObject::RetrieveContext method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveContext</b> method retrieves a context that was previously registered through the <a href="wdf.iwdfobject_assigncontext">IWDFObject::AssignContext</a> method.



## -syntax

````
HRESULT RetrieveContext(
  [out] void **ppvContext
);
````


## -parameters

### -param ppvContext [out]

A pointer to a buffer that receives a pointer to the previously registered context. 


## -returns
<b>RetrieveContext</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## -remarks
Because the context is not a Component Object Model (COM) interface, the driver must not treat the context as such. For example, the driver cannot call the <b>AddRef</b> method on the context.

For a code example of how to use the <b>RetrieveContext</b> method, see <a href="wdf.iwdfioqueue_getdevice">IWDFIoQueue::GetDevice</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>
</dt>
<dt>
<a href="wdf.iwdfioqueue_getdevice">IWDFIoQueue::GetDevice</a>
</dt>
<dt>
<a href="wdf.iwdfobject_assigncontext">IWDFObject::AssignContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFObject::RetrieveContext method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
