---
UID : NA:hidsdi
ms.assetid : 7d4500a3-b1b0-3eb9-a3be-1c32ed7651ce
ms.author : windowsdriverdev
ms.date : 01/18/18
ms.keywords : 
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : portal
---

# hidsdi.h header



hidsdi.h contains the following programming interfaces:





## Functions
| Title | Description |
| ---- |:---- |
| [HidD_FlushQueue](nf-hidsdi-hidd_flushqueue.md) | The HidD_FlushQueue routine deletes all pending input reports in a top-level collection's input queue. |
| [HidD_FreePreparsedData](nf-hidsdi-hidd_freepreparseddata.md) | The HidD_FreePreparsedData routine releases the resources that the HID class driver allocated to hold a top-level collection's preparsed data. |
| [HidD_GetAttributes](nf-hidsdi-hidd_getattributes.md) | The HidD_GetAttributes routine returns the attributes of a specified top-level collection. |
| [HidD_GetFeature](nf-hidsdi-hidd_getfeature.md) | The HidD_GetFeature routine returns a feature report from a specified top-level collection. |
| [HidD_GetHidGuid](nf-hidsdi-hidd_gethidguid.md) | The HidD_GetHidGuid routine returns the device interfaceGUID for HIDClass devices. |
| [HidD_GetIndexedString](nf-hidsdi-hidd_getindexedstring.md) | The HidD_GetIndexedString routine returns a specified embedded string from a top-level collection. |
| [HidD_GetInputReport](nf-hidsdi-hidd_getinputreport.md) | The HidD_GetInputReport routine returns an input reports from a top-level collection. |
| [HidD_GetManufacturerString](nf-hidsdi-hidd_getmanufacturerstring.md) | The HidD_GetManufacturerString routine returns a top-level collection's embedded string that identifies the manufacturer. |
| [HidD_GetNumInputBuffers](nf-hidsdi-hidd_getnuminputbuffers.md) | The HidD_GetNumInputBuffers routine returns the current size, in number of reports, of the ring buffer that the HID class driver uses to queue input reports from a specified top-level collection. |
| [HidD_GetPhysicalDescriptor](nf-hidsdi-hidd_getphysicaldescriptor.md) | The HidD_GetPhysicalDescriptor routine returns the embedded string of a top-level collection that identifies the collection's physical device. |
| [HidD_GetPreparsedData](nf-hidsdi-hidd_getpreparseddata.md) | The HidD_GetPreparsedData routine returns a top-level collection's preparsed data. |
| [HidD_GetProductString](nf-hidsdi-hidd_getproductstring.md) | The HidD_GetProductString routine returns the embedded string of a top-level collection that identifies the manufacturer's product. |
| [HidD_GetSerialNumberString](nf-hidsdi-hidd_getserialnumberstring.md) | The HidD_GetSerialNumberString routine returns the embedded string of a top-level collection that identifies the serial number of the collection's physical device. |
| [HidD_SetFeature](nf-hidsdi-hidd_setfeature.md) | The HidD_SetFeature routine sends a feature report to a top-level collection. |
| [HidD_SetNumInputBuffers](nf-hidsdi-hidd_setnuminputbuffers.md) | The HidD_SetNumInputBuffers routine sets the maximum number of input reports that the HID class driver ring buffer can hold for a specified top-level collection. |
| [HidD_SetOutputReport](nf-hidsdi-hidd_setoutputreport.md) | The HidD_SetOutputReport routine sends an output report to a top-level collection. |



## Structures
| Title | Description |
| ---- |:---- |
| [_HIDD_ATTRIBUTES](ns-hidsdi-_hidd_attributes.md) | The HIDD_ATTRIBUTES structure contains vendor information about a HIDClass device. |