---
title: IMimePropertySet DeleteProp method
description: Deletes the specified property.
ms.assetid: '0d3cf499-376d-41aa-b39c-2f00558634d4'
keywords: ["DeleteProp method Windows Mail (formerly Outlook Express)", "DeleteProp method Windows Mail (formerly Outlook Express) , IMimePropertySet interface", "IMimePropertySet interface Windows Mail (formerly Outlook Express) , DeleteProp method"]
topic_type:
- apiref
api_name:
- IMimePropertySet.DeleteProp
api_location:
- Inetcomm.dll
api_type:
- COM
---

# IMimePropertySet::DeleteProp method

Deletes the specified property.

## Syntax


```C++
HRESULT DeleteProp(
  [in]�LPCSTR pszName
);
```



## Parameters

<dl> <dt>

*pszName* \[in\]
</dt> <dd>

Type: **LPCSTR**

Specifies the property name or ID.

</dd> </dl>

## Return value

Type: **HRESULT**

Returns one of the following values.



| Return code                                                                                        | Description                                                                 |
|----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>               | Indicates success. <br/>                                              |
| <dl> <dt>**E\_FAIL**</dt> </dl>             | Indicates that an unknown error has occurred. <br/>                   |
| <dl> <dt>**E\_INVALIDARG**</dt> </dl>       | Indicates that *pszName* is **NULL**. <br/>                           |
| <dl> <dt>**MIME\_E\_NOT\_FOUND**</dt> </dl> | Indicates that *pszName* does not specify an existing property. <br/> |



�

## Remarks

A property ID can also be passed into this method through the *pszName* parameter using the PIDTOSTR macro.

## Requirements



|                                     |                                                                                                                |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�XP \[desktop apps only\]<br/>                                                                    |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                                           |
| Product<br/>                  | Outlook Express 6.0<br/>                                                                                 |
| Header<br/>                   | <dl> <dt>Mimeole.h</dt> </dl>                           |
| IDL<br/>                      | <dl> <dt>Mimeole.idl</dt> </dl>                         |
| DLL<br/>                      | <dl> <dt>Inetcomm.dll (version 6.0 or later)</dt> </dl> |



�

�




