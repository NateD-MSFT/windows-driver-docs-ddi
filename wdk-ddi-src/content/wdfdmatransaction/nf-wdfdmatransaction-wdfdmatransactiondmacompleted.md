---
UID: NF.wdfdmatransaction.WdfDmaTransactionDmaCompleted
title: WdfDmaTransactionDmaCompleted function
author: windows-driver-content
description: The WdfDmaTransactionDmaCompleted method notifies the framework that a device's DMA transfer operation is completed.
old-location: wdf\wdfdmatransactiondmacompleted.htm
old-project: wdf
ms.assetid: 83c1c4cb-b28b-4980-92fb-a1a49d95406e
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfDmaTransactionDmaCompleted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDmaTransactionDmaCompleted
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDmaTransactionDmaCompleted function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionDmaCompleted</b> method notifies the framework that a device's DMA transfer operation is completed.  



## -syntax

````
BOOLEAN WdfDmaTransactionDmaCompleted(
  _In_  WDFDMATRANSACTION DmaTransaction,
  _Out_ NTSTATUS          *Status
);
````


## -parameters

### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="wdf.wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param Status [out]

A pointer to a location that receives the status of the DMA transfer. For more information, see the following Remarks section.


## -returns
<b>WdfDmaTransactionDmaCompleted</b> returns <b>FALSE</b> and <i>Status</i> receives STATUS_MORE_PROCESSING_REQUIRED if additional transfers are needed to complete the DMA transaction. The method returns <b>TRUE</b> if no additional transfers are required. 

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
Framework-based drivers must call one of the following methods whenever a <a href="wdf.dma_transactions_and_dma_transfers">DMA transfer</a> is complete:

<b>WdfDmaTransactionDmaCompleted</b>


<a href="wdf.wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>



<a href="wdf.wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>


Typically, drivers call these methods from within an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> event callback function, after a device interrupt indicates the completion of a DMA transfer operation. A driver for a system-mode DMA device might call these methods from within an <a href="..\wdfdmatransaction\nc-wdfdmatransaction-evt_wdf_dma_transaction_dma_transfer_complete.md">EvtDmaTransactionDmaTransferComplete</a> event callback function.

The framework might divide a <a href="wdf.dma_transactions_and_dma_transfers">DMA transaction</a> into several DMA transfer operations. Therefore, the driver must examine the method's return value to determine if additional transfers are required. 

If the method returns <b>FALSE</b>, the <i>Status</i> location receives STATUS_MORE_PROCESSING_REQUIRED and additional DMA operations are required to complete the transaction. Typically, the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> event callback function does nothing else at this point. Instead, the framework calls the driver's <a href="wdf.evtprogramdma">EvtProgramDma</a> event callback function, so the callback function can begin the next transfer. 

If the method returns <b>TRUE</b>, no more transfers will occur for the specified transaction. In this case, a <i>Status</i> value of STATUS_SUCCESS means that the framework did not encounter any errors and the DMA transaction is complete. 

If the driver calls <a href="wdf.wdfdmatransactionstopsystemtransfer">WdfDmaTransactionStopSystemTransfer</a> before calling <b>WdfDmaTransactionDmaCompleted</b>, <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b> and a <i>Status</i> value of <b>STATUS_CANCELLED</b>.

For transactions that were set for <a href="https://msdn.microsoft.com/windows/hardware/drivers/wdf/">single transfer</a>, <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b> and a <i>Status</i> value of <b>STATUS_WDF_TOO_MANY_TRANSFERS</b> if the hardware fails to complete the transaction in a single transfer, even though initialization succeeded.
 	This could happen for hardware that reports residual transfers for each DMA operation. For example, the driver programs the device to write 64KB, but the device writes only 60KB.
   In this case, the driver might repeat the DMA operation or reset the device.

Any other value for <i>Status</i> means that the framework detected an error and the DMA transaction might not have been completed.

When <b>WdfDmaTransactionDmaCompleted</b> returns <b>TRUE</b>, the driver typically does the following:

Calls <a href="wdf.wdfobjectdelete">WdfObjectDelete</a> or <a href="wdf.wdfdmatransactionrelease">WdfDmaTransactionRelease</a> to delete or reuse the transaction object, respectively.

Completes the I/O request, if the DMA transaction is associated with an I/O request. (Drivers complete requests by calling <a href="wdf.wdfrequestcomplete">WdfRequestComplete</a> or <a href="wdf.wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>.)

For more information about completing DMA transfers, see <a href="wdf.completing_a_dma_transfer">Completing a DMA Transfer</a>.

The following code example is from the <a href="wdf.sample_kmdf_drivers">AMCC5933</a> sample driver. This example shows an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> callback function. The example notifies the framework that a DMA transfer has completed. If the framework indicates that this transfer is the last one for the DMA transaction, the code deletes the DMA transaction object and completes the associated I/O request.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdmatransaction.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a>
</dt>
<dt>
<a href="wdf.evtprogramdma">EvtProgramDma</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactioncreate">WdfDmaTransactionCreate</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactiondmacompletedwithlength">WdfDmaTransactionDmaCompletedWithLength</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactiondmacompletedfinal">WdfDmaTransactionDmaCompletedFinal</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactionrelease">WdfDmaTransactionRelease</a>
</dt>
<dt>
<a href="wdf.wdfobjectdelete">WdfObjectDelete</a>
</dt>
<dt>
<a href="wdf.wdfrequestcomplete">WdfRequestComplete</a>
</dt>
<dt>
<a href="wdf.wdfrequestcompletewithinformation">WdfRequestCompleteWithInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionDmaCompleted method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
