---
Description: Occurs when the InkCollector Class detects a cursor button that is down.
ms.assetid: 9ee2c19e-8a44-428b-a4c1-3c7250dcdeda
title: InkPicture.CursorButtonDown event
ms.topic: article
ms.date: 05/31/2018
---

# InkPicture.CursorButtonDown event

Occurs when the [**InkCollector Class**](inkcollector-class.md) detects a cursor button that is down.

## Syntax


```C++
void CursorButtonDown(
  [in] IInkCursor       *Cursor,
  [in] IInkCursorButton *Button
);
```



## Parameters

<dl> <dt>

*Cursor* \[in\]
</dt> <dd>

The [**IInkCursor**](/windows/desktop/api/msinkaut/nn-msinkaut-iinkcursor) object that generated the **CursorButtonDown** event.

</dd> <dt>

*Button* \[in\]
</dt> <dd>

The button that was pressed.

</dd> </dl>

## Return value

This event does not return a value.

## Remarks

A button on a pen tip is down when the user lowers the pen to the digitizer and starts tracing a stroke. A button on a barrel is down when the button is pressed.

When you press the right mouse button, you actually receive two **CursorButtonDown** events - one for right button pressed and one for left button pressed.

This event method is defined in the **\_IInkCollectorEvents**, **\_IInkOverlayEvents**, and **\_IInkPictureEvents** dispatch-only interface (dispinterfaces) with an ID of DISPID\_ICECursorButtonDown.

## Requirements



|                                     |                                                                                                                     |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP Tablet PC Edition \[desktop apps only\]<br/>                                                       |
| Minimum supported server<br/> | None supported<br/>                                                                                           |
| Header<br/>                   | <dl> <dt>Msinkaut.h (also requires Msinkaut\_i.c)</dt> </dl> |
| Library<br/>                  | <dl> <dt>InkObj.dll</dt> </dl>                               |



## See also

<dl> <dt>

[InkPicture](inkpicture-control-reference.md)
</dt> <dt>

[**CursorDown Event**](inkpicture-cursordown.md)
</dt> <dt>

[**CursorButtonUp Event**](inkpicture-cursorbuttonup.md)
</dt> <dt>

[**IInkCursor Interface**](/windows/desktop/api/msinkaut/nn-msinkaut-iinkcursor)
</dt> <dt>

[**IInkCursorButton Interface**](/windows/desktop/api/msinkaut/nn-msinkaut-iinkcursorbutton)
</dt> </dl>

 

 




