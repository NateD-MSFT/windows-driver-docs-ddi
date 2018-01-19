---
UID : NS:ksmedia.KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
title : KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
author : windows-driver-content
description : Describes region of interest (ROI) control properties in the PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST camera control property set.
old-location : stream\ksproperty_cameracontrol_region_of_interest_s.htm
old-project : stream
ms.assetid : 0a488d9f-1e34-4482-a2a8-7c160b00766c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, *PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S
req.alt-loc : Ksmedia.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S"
---

# KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure
Describes region of interest (ROI) control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_REGION_OF_INTEREST</b> camera control property set. The region of interest is a rectangle in the image that is used to focus the camera. This structure specifies property values that are used in requests to the camera driver.

## Syntax
````
typedef struct {
  RECT  FocusRect;
  BOOL  AutoFocusLock;
  BOOL  AutoExposureLock;
  BOOL  AutoWhitebalanceLock;
  union {
    ULONG Capabilities;
    ULONG Configuration;
  };
} KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S, *PKSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S;
````

## Members

        
            `AutoExposureLock`

            If <b>TRUE</b>, the device should lock the exposure to the current value.

This member should be ignored if <b>FocusRect</b> is not a valid value.
        
            `AutoFocusLock`

            If <b>TRUE</b>, the device should lock the focus to the current value.

This member should be ignored if <b>FocusRect</b> is not a valid value.
        
            `AutoWhitebalanceLock`

            If <b>TRUE</b>, the device should lock the white balance setting to the current value.

This member should be ignored if <b>FocusRect</b> is not a valid value.
        
            `FocusRect`

            A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the rectangular region in which the device should set the focus. This structure is available only to Windows apps.

If <b>FocusRect</b> is not a valid value, or if all members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure are zero, the device should focus the center of the image and the remaining members of this structure can be ignored.

The rectangle's coordinates are with respect to the preview video resolution.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksmedia.h (include Ksmedia.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj156041">KSPROPERTY_CAMERACONTROL_FLASH_PROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>