---
Description: Compresses the logical paging file (or directory) specified in the object path (this method is an extended version of the Compress method).
ms.assetid: ea99367b-4d5e-4cd2-aa89-d250d1161f8f
ms.tgt_platform: multiple
title: CompressEx method of the Win32_PageFile class
ms.topic: article
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- Win32_PageFile.CompressEx
api_type: 
- COM
api_location: 
- CIMWin32.dll
---

# CompressEx method of the Win32\_PageFile class

The **CompressEx** [WMI class](https://docs.microsoft.com/windows/desktop/WmiSdk/retrieving-a-class) method compresses the logical paging file (or directory) specified in the object path (this method is an extended version of the [**Compress**](compress-method-in-class-win32-directory.md) method).

This topic uses Managed Object Format (MOF) syntax. For more information about using this method, see [Calling a Method](https://docs.microsoft.com/windows/desktop/WmiSdk/calling-a-method).

## Syntax


```mof
uint32 CompressEx(
  [out]          string  StopFileName,
  [in, optional] string  StartFileName,
  [in, optional] boolean Recursive
);
```



## Parameters

<dl> <dt>

*StopFileName* \[out\]
</dt> <dd>

Name of the file or directory where the **CompressEx** method failed. This parameter is **null** if the method succeeds.

</dd> <dt>

*StartFileName* \[in, optional\]
</dt> <dd>

Names the child file or directory to use as a starting point for **CompressEx**. The *StartFileName* parameter is typically the *StopFileName* parameter specifying the file or directory at which an error occurred from the previous method call. If this parameter is **NULL**, the operation is performed on the file or directory specified in the **ExecMethod** call.

</dd> <dt>

*Recursive* \[in, optional\]
</dt> <dd>

If **true**, the change of ownership will be applied recursively to the files and directories within the directory specified by the [**CIM\_LogicalFile**](cim-logicalfile.md) instance.

> [!Note]  
> For file instances, the *Recursive* parameter is ignored.

 

</dd> </dl>

## Return value

Returns a value of 0 (zero) if the file was successfully compressed, and any other number to indicate an error.

<dl> <dt>

**0**
</dt> <dd>

The request was successful.

</dd> <dt>

**2**
</dt> <dd>

Access was denied.

</dd> <dt>

**8**
</dt> <dd>

An unspecified failure occurred.

</dd> <dt>

**9**
</dt> <dd>

The name specified was not valid.

</dd> <dt>

**10**
</dt> <dd>

The object specified already exists.

</dd> <dt>

**11**
</dt> <dd>

The file system is not NTFS.

</dd> <dt>

**12**
</dt> <dd>

The platform is not Windows.

</dd> <dt>

**13**
</dt> <dd>

The drive is not the same.

</dd> <dt>

**14**
</dt> <dd>

The directory is not empty.

</dd> <dt>

**15**
</dt> <dd>

There has been a sharing violation.

</dd> <dt>

**16**
</dt> <dd>

The start file specified was not valid.

</dd> <dt>

**17**
</dt> <dd>

A privilege required for the operation is not held.

</dd> <dt>

**21**
</dt> <dd>

A parameter specified is not valid.

</dd> </dl>

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[Operating System Classes](https://docs.microsoft.com/previous-versions//aa392727(v=vs.85))
</dt> <dt>

[**Win32\_PageFile**](win32-pagefile.md)
</dt> </dl>

 

 




