---
Description: 'In Windows Vista, Microsoft Media Foundation exposes metadata through the IMFMetadata interface.'
ms.assetid: 'a26e40c2-1717-4a13-8bf0-e41376a8d317'
title: Metadata Providers in Windows Vista
---

# Metadata Providers in Windows Vista

In Windows Vista, Microsoft Media Foundation exposes metadata through the [**IMFMetadata**](imfmetadata.md) interface.

## Reading Metadata

To read metadata from a media source, perform the following steps:

1.  Get a pointer to the [**IMFMediaSource**](imfmediasource.md) interface of the media source. You can use the [**IMFSourceResolver**](imfsourceresolver.md) interface to get an **IMFMediaSource** pointer.
2.  Call [**IMFMediaSource::CreatePresentationDescriptor**](imfmediasource-createpresentationdescriptor.md) to get the media source's presentation descriptor.
3.  Call [**MFGetService**](mfgetservice.md) on the media source to get a pointer to the [**IMFMetadataProvider**](imfmetadataprovider.md) interface. In the *guidService* parameter of **MFGetService**, specify the value **MF\_METADATA\_PROVIDER\_SERVICE**. If the source does not support the **IMFMetadataProvider** interface, **MFGetService** returns **MF\_E\_UNSUPPORTED\_SERVICE**.
4.  Call [**IMFMetadataProvider::GetMFMetadata**](imfmetadataprovider-getmfmetadata.md) and pass in a pointer to the presentation descriptor. This method returns a pointer to the [**IMFMetadata**](imfmetadata.md) interface.
    -   To get stream-level metadata first call [**IMFStreamDescriptor::GetStreamIdentifier**](imfstreamdescriptor-getstreamidentifier.md) to get the stream identifier. Then pass the stream identifier in the *dwStreamIdentifier* parameter of [**GetMFMetadata**](imfmetadataprovider-getmfmetadata.md).
    -   To get presentation-level metadata, set *dwStreamIdentifier* to zero.
5.  \[Optional\] Call [**IMFMetadata::GetAllLanguages**](imfmetadata-getalllanguages.md) to get a list of the languages in which metadata is available. Languages are identified using RFC 1766-compliant language tags.
6.  \[Optional\] Call [**IMFMetadata::SetLanguage**](imfmetadata-setlanguage.md) to select the language.
7.  \[Optional\] Call [**IMFMetadata::GetAllPropertyNames**](imfmetadata-getallpropertynames.md) to get a list of the names of all the metadata properties for this stream or presentation.
8.  Call [**IMFMetadata::GetProperty**](imfmetadata-getproperty.md) to get a specific metadata property value, passing in the name of the property.

The following code shows steps 2–4:


```C++
HRESULT GetMetadata(
    IMFMediaSource *pSource, IMFMetadata **ppMetadata, DWORD dwStream = 0)
{
    IMFPresentationDescriptor *pPD = NULL;
    IMFMetadataProvider *pProvider = NULL;

    HRESULT hr = pSource->CreatePresentationDescriptor(&amp;pPD);
    if (FAILED(hr))
    {
        goto done;
    }

    hr = MFGetService(
        pSource, MF_METADATA_PROVIDER_SERVICE, IID_PPV_ARGS(&amp;pProvider));

    if (FAILED(hr))
    {
        goto done;
    }

    hr = pProvider->GetMFMetadata(pPD, dwStream, 0, ppMetadata);

done:
    SafeRelease(&amp;pPD);
    SafeRelease(&amp;pProvider);
    return hr;
}
```



The following code shows steps 7–8. Assume that `DisplayProperty` is a function that displays a **PROPVARIANT** value.


```C++
HRESULT DisplayMetadata(IMFMetadata *pMetadata)
{
    PROPVARIANT varNames;
    HRESULT hr = pMetadata->GetAllPropertyNames(&amp;varNames);
    if (FAILED(hr))
    {
        return hr;
    }

    for (ULONG i = 0; i < varNames.calpwstr.cElems; i++)
    {
        wprintf(L"%s\n", varNames.calpwstr.pElems[i]);

        PROPVARIANT varValue;
        hr = pMetadata->GetProperty( varNames.calpwstr.pElems[i], &amp;varValue );
        if (SUCCEEDED(hr))
        {
            DisplayProperty(varValue);
            PropVariantClear(&amp;varValue);
        }
    }

    PropVariantClear(&amp;varNames);
    return hr;
}
```



## Related topics

<dl> <dt>

[Media Metadata](media-metadata.md)
</dt> <dt>

[Shell Metadata Providers](shell-metadata-providers.md)
</dt> </dl>

 

 


