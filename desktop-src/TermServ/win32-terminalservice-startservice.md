---
title: StartService method of the Win32\_Service class
description: Attempts to place the referenced service into its startup state.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: '4DA05C48-03A0-4D4B-9E69-0404393C219C'
ms.prod: 'windows-server-dev'
ms.technology: 'remote-desktop-services'
ms.tgt_platform: multiple
keywords: ["StartService method Remote Desktop Services", "StartService method Remote Desktop Services , Win32_Service class", "Win32_Service class Remote Desktop Services , StartService method"]
topic_type:
- apiref
api_name:
- Win32_Service.StartService
api_location:
- TSCfgWmi.dll
api_type:
- COM
---

# StartService method of the Win32\_Service class

The **StartService** method attempts to place the referenced service into its startup state.

This topic uses Managed Object Format (MOF) syntax. For more information about using this method, see [Calling a Method](https://msdn.microsoft.com/library/aa384832).

## Syntax


```mof
uint32 StartService();
```



## Parameters

This method has no parameters.

## Return value

Returns one of the values listed in the following list, or any other value to indicate an error. For additional error codes, see [**WMI Error Constants**](https://msdn.microsoft.com/library/aa394559) or [**WbemErrorEnum**](https://msdn.microsoft.com/library/aa393978). For general **HRESULT** values, see [System Error Codes](https://msdn.microsoft.com/library/windows/desktop/ms681381).

<dl> <dt>

**0**
</dt> <dd>

The request was accepted.

</dd> <dt>

**1**
</dt> <dd>

The request is not supported.

</dd> <dt>

**2**
</dt> <dd>

The user did not have the necessary access.

</dd> <dt>

**3**
</dt> <dd>

The service cannot be stopped because other services that are running are dependent on it.

</dd> <dt>

**4**
</dt> <dd>

The requested control code is not valid, or it is unacceptable to the service.

</dd> <dt>

**5**
</dt> <dd>

The requested control code cannot be sent to the service because the state of the service ([**Win32\_BaseService**](https://msdn.microsoft.com/library/aa394073).**State** property) is equal to 0, 1, or 2.

</dd> <dt>

**6**
</dt> <dd>

The service has not been started.

</dd> <dt>

**7**
</dt> <dd>

The service did not respond to the start request in a timely fashion.

</dd> <dt>

**8**
</dt> <dd>

Unknown failure when starting the service.

</dd> <dt>

**9**
</dt> <dd>

The directory path to the service executable file was not found.

</dd> <dt>

**10**
</dt> <dd>

The service is already running.

</dd> <dt>

**11**
</dt> <dd>

The database to add a new service is locked.

</dd> <dt>

**12**
</dt> <dd>

A dependency this service relies on has been removed from the system.

</dd> <dt>

**13**
</dt> <dd>

The service failed to find the service needed from a dependent service.

</dd> <dt>

**14**
</dt> <dd>

The service has been disabled from the system.

</dd> <dt>

**15**
</dt> <dd>

The service does not have the correct authentication to run on the system.

</dd> <dt>

**16**
</dt> <dd>

This service is being removed from the system.

</dd> <dt>

**17**
</dt> <dd>

The service has no execution thread.

</dd> <dt>

**18**
</dt> <dd>

The service has circular dependencies when it starts.

</dd> <dt>

**19**
</dt> <dd>

A service is running under the same name.

</dd> <dt>

**20**
</dt> <dd>

The service name has invalid characters.

</dd> <dt>

**21**
</dt> <dd>

Invalid parameters have been passed to the service.

</dd> <dt>

**22**
</dt> <dd>

The account under which this service runs is either invalid or lacks the permissions to run the service.

</dd> <dt>

**23**
</dt> <dd>

The service exists in the database of services available from the system.

</dd> <dt>

**24**
</dt> <dd>

The service is currently paused in the system.

</dd> </dl>

## Remarks

Although there might appear to be no practical difference between a service that is stopped and a service that is paused, the two states appear differently to the SCM. A stopped service is a service that is not running and must go through the entire service start procedure. A paused service, however, is still running but has had its functioning is suspended. Because of this, a paused service does not need to go through the entire service start procedure but needs a different procedure to resume functioning.

You must use the proper method to start a service that has been stopped or to resume a service that has been paused. The [**Win32\_Service**](https://msdn.microsoft.com/library/aa394418) methods **StartService** and [**ResumeService**](win32-terminalservice-resumeservice.md) should be used in the following situations:

-   If a service is currently stopped, you must use the **StartService** method to restart it; [**ResumeService**](win32-terminalservice-resumeservice.md) cannot start a service that is currently stopped.
-   If a service is paused, you must use [**ResumeService**](win32-terminalservice-resumeservice.md). If you use the **StartService** method on a paused service, you receive the message, "The service is already running." However, the service remains paused until the resume service control code is sent to it.

If you start a stopped service that depends on another service, then both services are started. When a service is started with this method, any dependent services are not automatically started. You must use the association class [**Win32\_DependentService**](https://msdn.microsoft.com/library/aa394120) and the [Associators Of](https://msdn.microsoft.com/library/aa384793) query to locate the dependents and start them separately.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server�2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMv2\\TerminalServices<br/>                                                |
| MOF<br/>                      | <dl> <dt>TSCfgWmi.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>TSCfgWmi.dll</dt> </dl> |



## See also

<dl> <dt>

[**Win32\_Service**](https://msdn.microsoft.com/library/aa394418)
</dt> <dt>

[Operating System Classes](https://msdn.microsoft.com/library/dn792258)
</dt> <dt>

[**Win32\_TerminalService**](win32-terminalservice.md)
</dt> <dt>

[WMI Tasks: Services](https://msdn.microsoft.com/library/aa394602)
</dt> </dl>

�

�




