---
title: ID3DX11EffectVectorVariable GetBoolVectorArray method
description: Get an array of four-component vectors that contain boolean data.
ms.assetid: f600a480-e68e-4b05-8c76-2fe30520172b
keywords:
- GetBoolVectorArray method Direct3D 11
- GetBoolVectorArray method Direct3D 11 , ID3DX11EffectVectorVariable interface
- ID3DX11EffectVectorVariable interface Direct3D 11 , GetBoolVectorArray method
topic_type:
- apiref
api_name:
- ID3DX11EffectVectorVariable.GetBoolVectorArray
api_location:
- N/A
- N/A.dll
api_type:
- COM
ms.topic: article
ms.date: 05/31/2018
---

# ID3DX11EffectVectorVariable::GetBoolVectorArray method

Get an array of four-component vectors that contain boolean data.

## Syntax


```C++
HRESULT GetBoolVectorArray(
   BOOL *pData,
   UINT Offset,
   UINT Count
);
```



## Parameters

<dl> <dt>

*pData* 
</dt> <dd>

Type: **[**BOOL**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types)\***

A pointer to the start of the data to set.

</dd> <dt>

*Offset* 
</dt> <dd>

Type: **[**UINT**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types)**

Must be set to 0; this is reserved for future use.

</dd> <dt>

*Count* 
</dt> <dd>

Type: **[**UINT**](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types)**

The number of array elements to set.

</dd> </dl>

## Return value

Type: **[**HRESULT**](https://msdn.microsoft.com/en-us/library/Bb401631(v=MSDN.10).aspx)**

Returns one of the following [Direct3D 11 Return Codes](d3d11-graphics-reference-returnvalues.md).

## Remarks

> [!Note]  
> The DirectX SDK does not supply any compiled binaries for effects. You must use Effects 11 source to build your effects-type application. For more information about using Effects 11 source, see [Differences Between Effects 10 and Effects 11](d3d11-graphics-programming-guide-effects-differences.md).

 

## Requirements



|                    |                                                                                                                                              |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx11effect.h</dt> </dl>                                                    |
| Library<br/> | <dl> <dt>N/A (An Effects 11 library is available online as shared source.)</dt> </dl> |



## See also

<dl> <dt>

[ID3DX11EffectVectorVariable](id3dx11effectvectorvariable.md)
</dt> </dl>

 

 





