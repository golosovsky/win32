---
Description: 'Retrieves a value that specifies an external user account.'
audience: developer
author: 'REDMOND\\markl'
manager: 'REDMOND\\mbaldwin'
ms.assetid: '0b61792b-e5f7-4f01-a935-d7ce28ebc5c0'
ms.prod: 'windows-server-dev'
ms.technology: 'active-directory-rights-management'
ms.tgt_platform: multiple
title: 'Constants.ExcludedExternalUserType property'
---

# Constants.ExcludedExternalUserType property

The **ExcludedExternalUserType** property retrieves a value that specifies an external user account.

This property is read-only.

## Syntax


```VB
Constants.ExcludedExternalUserType
```



## Property value

This property returns an integer value (0x2) that identifies an external user account.

## Remarks

The property value can be used with the [**UserType**](excludeduseraccount-usertype-property.md) property on the [**ExcludedUserAccount**](excludeduseraccount-object.md) object.

## Examples


```VB
DIM config_manager
DIM admin_role

' *******************************************************************
' Create and initialize a ConfigurationManager object.

SUB InitObject()

  CALL WScript.Echo( "Create ConfigurationManager object...")
  SET config_manager = CreateObject _
    ("Microsoft.RightsManagementServices.Admin.ConfigurationManager")      
  CheckError()
    
  CALL WScript.Echo( "Initialize...")
  admin_role=config_manager.Initialize(false,"localhost",80,"","","")
  CheckError()

END SUB

' *******************************************************************
' Retrieve the type of each excluded user.

SUB GetExclUserType()

  DIM exclPolicy
  DIM exclUser
  DIM exclUserColl
  DIM constant

  ' Retrieve the Constants object.
  SET constant = config_manager.Constants

  ' Retrieve the ExclusionPolicy object.
  SET exclPolicy = config_manager.Enterprise.ExclusionPolicy
  CheckError()

  ' Retrieve the ExcludedUSerAccountCollection object.
  SET exclUserColl = exclusionPolicy.UserAccounts
  CheckError()

 ' Loop through the collection and retrieve the user type.
  For Each exclUser in exclUserColl
   CALL WScript.Echo("UserId: " & exclUser.UserId)
   IF exclUser.UserType = constant.ExcludedDomainUserType THEN
    CALL WScript.Echo("Excluded user is domain type.")
   ELSEIF exclUser.UserType=constant.ExcludedExternalUserType THEN
    CALL WScript.Echo("Excluded user is external type.")
   ELSEIF exclUser.UserType=constant.ExcludedFederationUserType THEN
    CALL WScript.Echo("Excluded user is ADFS type.")
   ELSE
    CALL WScript.Echo("Excluded user type cannot be determined.")
   END IF
  Next

END SUB

' *******************************************************************
' Error checking function.

FUNCTION CheckError()
  CheckError = Err.number
  IF Err.number <> 0 THEN
    CALL WScript.Echo( vbTab & "*****Error Number: " _
                       & Err.number _
                       & " Desc:" _
                       & Err.Description _
                       & "*****")
    WScript.StdErr.Write(Err.Description)
    WScript.Quit( Err.number )
  END IF
END FUNCTION
```



## Requirements



|                                     |                                                                                                                         |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                                               |
| Minimum supported server<br/> | Windows Server�2008<br/>                                                                                          |
| Assembly<br/>                 | <dl> <dt>Microsoft.RightsManagementServices.Admin.dll</dt> </dl> |



## See also

<dl> <dt>

[**Constants**](constants-object.md)
</dt> <dt>

[**ExcludedDomainUserType**](constants-excludeddomainusertype-property.md)
</dt> <dt>

[**ExcludedFederationUserType**](constants-excludedfederationusertype-property.md)
</dt> </dl>

�

�



