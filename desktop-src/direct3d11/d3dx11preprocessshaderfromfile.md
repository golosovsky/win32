---
title: D3DX11PreprocessShaderFromFile function
description: Note The D3DX (D3DX 9, D3DX 10, and D3DX 11) utility library is deprecated for Windows�8 and is not supported for Windows Store apps.�Note Instead of using this function, we recommend that you use the D3DPreprocess API.�Create a shader from a file without compiling it.
ms.assetid: 'aab08efd-b6b0-44e5-bd68-f32c242d9e94'
keywords: ["D3DX11PreprocessShaderFromFile function Direct3D 11"]
topic_type:
- apiref
api_name:
- D3DX11PreprocessShaderFromFile
api_location:
- D3DX11.lib
- D3DX11.dll
api_type:
- LibDef
---

# D3DX11PreprocessShaderFromFile function

> [!Note]  
> The D3DX (D3DX 9, D3DX 10, and D3DX 11) utility library is deprecated for Windows�8 and is not supported for Windows Store apps.

�

> [!Note]  
> Instead of using this function, we recommend that you use the [**D3DPreprocess**](https://msdn.microsoft.com/library/windows/desktop/dd607332) API.

�

Create a shader from a file without compiling it.

## Syntax


```C++
HRESULT D3DX11PreprocessShaderFromFile(
  _In_��������LPCTSTR �����������pFileName,
  _In_��const D3D11_SHADER_MACRO *pDefines,
  _In_��������LPD3D10INCLUDE ����pInclude,
  _In_��������ID3DX11ThreadPump �*pPump,
  _Out_�������ID3D10Blob ��������**ppShaderText,
  _Out_�������ID3D10Blob ��������**ppErrorMsgs,
  _Out_�������HRESULT �����������*pHResult
);
```



## Parameters

<dl> <dt>

*pFileName* \[in\]
</dt> <dd>

Type: **[**LPCTSTR**](https://msdn.microsoft.com/library/windows/desktop/aa383751)**

Name of the shader file.

</dd> <dt>

*pDefines* \[in\]
</dt> <dd>

Type: **const D3D11\_SHADER\_MACRO\***

A NULL-terminated array of shader macros; set this to **NULL** to specify no macros.

</dd> <dt>

*pInclude* \[in\]
</dt> <dd>

Type: **[**LPD3D10INCLUDE**](https://msdn.microsoft.com/library/windows/desktop/bb173775)**

A pointer to an include interface; set this to **NULL** to specify there is no include file.

</dd> <dt>

*pPump* \[in\]
</dt> <dd>

Type: **[**ID3DX11ThreadPump**](id3dx11threadpump.md)\***

A pointer to a thread pump interface (see [**ID3DX11ThreadPump Interface**](id3dx11threadpump.md)). Use **NULL** to specify that this function should not return until it is completed.

</dd> <dt>

*ppShaderText* \[out\]
</dt> <dd>

Type: **[**ID3D10Blob**](https://msdn.microsoft.com/library/windows/desktop/bb173507)\*\***

A pointer to memory that contains the uncompiled shader.

</dd> <dt>

*ppErrorMsgs* \[out\]
</dt> <dd>

Type: **[**ID3D10Blob**](https://msdn.microsoft.com/library/windows/desktop/bb173507)\*\***

The address of a pointer to memory that contains effect-creation errors, if any occurred.

</dd> <dt>

*pHResult* \[out\]
</dt> <dd>

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)\***

A pointer to the return value. May be **NULL**. If *pPump* is not **NULL**, then *pHResult* must be a valid memory location until the asynchronous execution completes.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

The return value is one of the values listed in [Direct3D 11 Return Codes](d3d11-graphics-reference-returnvalues.md).

## Requirements



|                    |                                                                                          |
|--------------------|------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX11async.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3DX11.lib</dt> </dl>    |



## See also

<dl> <dt>

[D3DX Functions](d3d11-graphics-reference-d3dx11-functions.md)
</dt> </dl>

�

�




