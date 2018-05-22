---
title: AtaPortCompleteAllActiveRequests routine
description: The AtaPortCompleteAllActiveRequests routine completes all active IRBs for the indicated device.Note The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
ms.assetid: 'e17b1a76-ab1e-4263-9e4a-42c6f2066de1'
keywords: ["AtaPortCompleteAllActiveRequests routine Storage Devices"]
topic_type:
- apiref
api_name:
- AtaPortCompleteAllActiveRequests
api_location:
- ataport.lib
- ataport.dll
- pciidex.lib
- pciidex.dll
api_type:
- LibDef
---

# AtaPortCompleteAllActiveRequests routine

The **AtaPortCompleteAllActiveRequests** routine completes all active IRBs for the indicated device.

> [!Note]  
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver) and [Storport miniport](https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers) driver models.

�

## Syntax


```C++
VOID AtaPortCompleteAllActiveRequests(
  _In_�PVOID ChannelExtension,
  _In_�UCHAR Target,
  _In_�UCHAR Lun,
  _In_�UCHAR IrbStatus
);
```



## Parameters

<dl> <dt>

*ChannelExtension* \[in\]
</dt> <dd>

A pointer to the channel extension.

</dd> <dt>

*Target* \[in\]
</dt> <dd>

Specifies the target identifier of the device.

</dd> <dt>

*Lun* \[in\]
</dt> <dd>

Specifies the logical unit number of the device.

</dd> <dt>

*IrbStatus* \[in\]
</dt> <dd>

Specifies the status with which the requests will be completed.

</dd> </dl>

## Return value

None

## Remarks

The **AtaPortCompleteAllActiveRequests** routine completes all active IRBs on the device as indicated by the *Target* and *Lun* parameters. Miniport drivers use this routine to complete all active IRPs if there is a reset. Miniport drivers can complete IRBs on all devices concurrently by assigning a value of IDE\_UNTAGGED to the *Target* and *Lun* parameters, instead of specifying a specific device.

The miniport driver must not call this routine from the [**IdeHwInterrupt**](idehwinterrupt.md) routine.

## Requirements



|                            |                                                                                                                                                           |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Target platform<br/> | <dl> <dt>Desktop</dt> </dl>                                                                        |
| Header<br/>          | <dl> <dt>Irb.h (include Ata.h or Irb.h)</dt> </dl>                                                 |
| Library<br/>         | <dl> <dt>Ataport.lib; </dt> <dt>Pciidex.lib</dt> </dl> |



## See also

<dl> <dt>

[**IdeHwInterrupt**](idehwinterrupt.md)
</dt> </dl>

�

�

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20AtaPortCompleteAllActiveRequests%20routine%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





