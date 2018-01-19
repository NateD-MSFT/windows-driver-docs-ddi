---
UID : NS:bdatypes.tagKS_BDA_FRAME_INFO
title : tagKS_BDA_FRAME_INFO
author : windows-driver-content
description : The KS_BDA_FRAME_INFO structure describes BDA extensions to the KSSTREAM_HEADER structure, which describes a packet of data to be read from or written to a streaming driver pin.
old-location : stream\ks_bda_frame_info.htm
old-project : stream
ms.assetid : df261323-f372-49e7-990a-03c1c5cb743d
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : tagKS_BDA_FRAME_INFO, *PKS_BDA_FRAME_INFO, KS_BDA_FRAME_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bdatypes.h
req.include-header : Bdamedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KS_BDA_FRAME_INFO
req.alt-loc : bdatypes.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PKS_BDA_FRAME_INFO, KS_BDA_FRAME_INFO"
---

# tagKS_BDA_FRAME_INFO structure
The KS_BDA_FRAME_INFO structure describes BDA extensions to the KSSTREAM_HEADER structure, which describes a packet of data to be read from or written to a streaming driver pin.

## Syntax
````
typedef struct tagKS_BDA_FRAME_INFO {
  ULONG ExtendedHeaderSize;
  DWORD dwFrameFlags;
  ULONG ulEvent;
  ULONG ulChannelNumber;
  ULONG ulSubchannelNumber;
  ULONG ulReason;
} KS_BDA_FRAME_INFO, *PKS_BDA_FRAME_INFO;
````

## Members

        
            `dwFrameFlags`

            Flags specific to BDA extensions.
        
            `ExtendedHeaderSize`

            Size, in bytes, of the BDA extensions described in this extended header structure.
        
            `ulChannelNumber`

            Channel number of a television program.
        
            `ulEvent`

            Identifier of an event.
        
            `ulReason`

            Identifies the reason the packet was transferred.
        
            `ulSubchannelNumber`

            Subchannel number of a television program.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h (include Bdamedia.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_BDA_FRAME_INFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>