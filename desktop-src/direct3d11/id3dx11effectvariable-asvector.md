---
title: ID3DX11EffectVariable AsVector method
description: Get a vector variable.
ms.assetid: 995bd9f3-1417-4048-9a23-4dcb3864c77d
keywords:
- AsVector method Direct3D 11
- AsVector method Direct3D 11 , ID3DX11EffectVariable interface
- ID3DX11EffectVariable interface Direct3D 11 , AsVector method
topic_type:
- apiref
api_name:
- ID3DX11EffectVariable.AsVector
api_location:
- N/A
- N/A.dll
api_type:
- COM
ms.topic: article
ms.date: 05/31/2018
---

# ID3DX11EffectVariable::AsVector method

Get a vector variable.

## Syntax


```C++
ID3DX11EffectVectorVariable* AsVector();
```



## Parameters

This method has no parameters.

## Return value

Type: **[**ID3DX11EffectVectorVariable**](id3dx11effectvectorvariable.md)\***

A pointer to a vector variable. See [**ID3DX11EffectVectorVariable**](id3dx11effectvectorvariable.md).

## Remarks

AsVector returns a version of the effect variable that has been specialized to a vector variable. Similar to a cast, this specialization will return an invalid object if the effect variable does not contain vector data.

Applications can test the returned object for validity by calling [**IsValid**](id3dx11effectvariable-isvalid.md).

> [!Note]  
> The DirectX SDK does not supply any compiled binaries for effects. You must use Effects 11 source to build your effects-type application. For more information about using Effects 11 source, see [Differences Between Effects 10 and Effects 11](d3d11-graphics-programming-guide-effects-differences.md).

 

## Requirements



|                    |                                                                                                                                              |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx11effect.h</dt> </dl>                                                    |
| Library<br/> | <dl> <dt>N/A (An Effects 11 library is available online as shared source.)</dt> </dl> |



## See also

<dl> <dt>

[ID3DX11EffectVariable](id3dx11effectvariable.md)
</dt> </dl>

 

 





