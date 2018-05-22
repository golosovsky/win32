---
title: ID2D1RenderTarget Clear methods
description: Clears the drawing area to the specified color.
ms.assetid: '3bfec923-17fc-479a-a760-9baab2ff3a56'
keywords: ["Clear methods Direct2D"]
topic_type:
- apiref
api_location:
- D2d1.dll
api_type:
- DllExport
---

# ID2D1RenderTarget::Clear methods

Clears the drawing area to the specified color.

### Overload list



| Method                                                                 | Description                                                 |
|:-----------------------------------------------------------------------|:------------------------------------------------------------|
| [**Clear(D2D1\_COLOR\_F\*)**](id2d1rendertarget-clear-ptr-color-f.md) | Clears the drawing area to the specified color. <br/> |
| [**Clear(D2D1\_COLOR\_F&)**](id2d1rendertarget-clear-ref-color-f.md)  | Clears the drawing area to the specified color. <br/> |



## Remarks

Direct2D interprets the *clearColor* as straight alpha (not premultiplied). If the render target's alpha mode is [**D2D1\_ALPHA\_MODE\_IGNORE**](d2d1-alpha-mode.md), the alpha channel of *clearColor* is ignored and replaced with 1.0f (fully opaque).

If the render target has an active clip (specified by [**PushAxisAlignedClip**](id2d1rendertarget-pushaxisalignedclip-ptr-d2d-rect-f-d2d1-antialias-mode.md)), the clear command is only applied to the area within the clip region.

## Examples

The following example uses the **Clear** method to create a white background before rendering other content.


```C++
//  Called whenever the application needs to display the client
//  window. This method writes "Hello, World"
//
//  Note that this function will automatically discard device-specific
//  resources if the Direct3D device disappears during function
//  invocation, and will recreate the resources the next time it's
//  invoked.
//
HRESULT DemoApp::OnRender()
{
    HRESULT hr;

    hr = CreateDeviceResources();

    if (SUCCEEDED(hr))
    {
        static const WCHAR sc_helloWorld[] = L"Hello, World!";

        // Retrieve the size of the render target.
        D2D1_SIZE_F renderTargetSize = m_pRenderTarget->GetSize();

        m_pRenderTarget->BeginDraw();

        m_pRenderTarget->SetTransform(D2D1::Matrix3x2F::Identity());

        m_pRenderTarget->Clear(D2D1::ColorF(D2D1::ColorF::White));

        m_pRenderTarget->DrawText(
            sc_helloWorld,
            ARRAYSIZE(sc_helloWorld) - 1,
            m_pTextFormat,
            D2D1::RectF(0, 0, renderTargetSize.width, renderTargetSize.height),
            m_pBlackBrush
            );

        hr = m_pRenderTarget->EndDraw();

        if (hr == D2DERR_RECREATE_TARGET)
        {
            hr = S_OK;
            DiscardDeviceResources();
        }
    }

    return hr;
}
```



## Requirements



|                    |                                                                                     |
|--------------------|-------------------------------------------------------------------------------------|
| Library<br/> | <dl> <dt>D2d1.lib</dt> </dl> |
| DLL<br/>     | <dl> <dt>D2d1.dll</dt> </dl> |



## See also

<dl> <dt>

[**ID2D1RenderTarget**](id2d1rendertarget.md)
</dt> </dl>

�

�




