---
UID : NF:winspool.FindFirstPrinterChangeNotification
title : FindFirstPrinterChangeNotification function
author : windows-driver-content
description : Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location : print\findfirstprinterchangenotification.htm
old-project : print
ms.assetid : f6d2034a-0906-42ea-a4bd-9cdb1b36c5cf
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : FindFirstPrinterChangeNotification
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : winspool.h
req.include-header : Winspool.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FindFirstPrinterChangeNotification
req.alt-loc : WinSpool.drv
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : WinSpool.lib
req.dll : WinSpool.drv
req.irql : 
req.typenames : BIDI_TYPE
req.product : Windows 10 or later.
---


# FindFirstPrinterChangeNotification function


## Syntax

````
BOOL FindFirstPrinterChangeNotification(
   HANDLE hPrinter,
   DWORD  fdwFlags,
   DWORD  fdwOptions,
   HANDLE hNotify,
   PDWORD pfdwStatus,
   PVOID  pPrinterNotifyOptions,
   PVOID  pPrinterNotifyInit
);
````

## Parameters

`hPrinter`

Caller-supplied printer handle, identifying the printer for which event notification is being requested. This handle must have been previously obtained from OpenPrinter (described in the Microsoft Windows SDK documentation).

`fdwFilter`



`fdwOptions`

Not used.

`pPrinterNotifyOptions`

Caller-supplied pointer to a PRINTER_NOTIFY_OPTIONS structure (described in the Windows SDK documentation).


## Return Value

If the operation succeeds, the function should return <b>TRUE</b>. Otherwise the function should return <b>FALSE</b>.

## Remarks

When the spooler calls a print provider's <b>FindFirstPrinterChangeNotification</b> function, <i>fdwFlags</i> identifies the printer events for which notification is being requested. Additionally, <i>pPrinterNotifyOptions</i> identifies the types of information that the print provider should send to the spooler when one of the specified events occurs.

For a list of the types of notifications an application can request, and for a list of the types of information that can be used to describe an event, see the Windows SDK documentation's description of <b>FindFirstPrinterChangeNotification</b>. Types of events for which an application might request notification include adding or deleting a print job or form. Types of information an application might request include job or form parameters.

If the print provider does not request polling (that is, it does not set PRINTER_NOTIFY_STATUS_POLL in <i>pfdwStatus</i>), it must notify the spooler when events identified by <i>pfwFlags</i> occur. The print provider must supply the types of information identified by <i>pPrinterNotifyOptions</i>, by calling <a href="..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md">PartialReplyPrinterChangeNotification</a> or <a href="..\winsplp\nf-winsplp-replyprinterchangenotification.md">ReplyPrinterChangeNotification</a>.

If the provider does request polling (that is, it sets PRINTER_NOTIFY_STATUS_POLL), it should not call <b>ReplyPrinterChangeNotification</b>. Instead, the spooler signals the application at regular intervals.

Both polled and nonpolled print provider must return the current state of all requested information types whenever its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a> function is called.

For additional information, see <a href="https://msdn.microsoft.com/e75c6f89-9cef-4900-af89-edf1f7f786c7">Supporting Printer Change Notifications</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winspool.h (include Winspool.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md">PartialReplyPrinterChangeNotification</a>
</dt>
<dt>
<a href="..\winsplp\nf-winsplp-replyprinterchangenotification.md">ReplyPrinterChangeNotification</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20FindFirstPrinterChangeNotification function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>