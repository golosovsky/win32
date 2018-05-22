---
Description: 'The CIM\_ComputerSystemIRQ class represents an association between a computer system and its available interrupt request lines (IRQs).'
audience: developer
author: 'REDMOND\\markl'
manager: 'REDMOND\\markl'
ms.assetid: 'c2a1f231-1f8e-48b2-9afe-fa798e6a8a1d'
ms.prod: 'windows-server-dev'
ms.technology:
- cimwin32
- 'windows-management-instrumentation'
ms.tgt_platform: multiple
title: 'CIM\_ComputerSystemIRQ class'
---

# CIM\_ComputerSystemIRQ class

The **CIM\_ComputerSystemIRQ** class represents an association between a computer system and its available interrupt request lines (IRQs).

> \[!Important\]  
> The DMTF (Distributed Management Task Force) CIM (Common Information Model) classes are the parent classes upon which WMI classes are built. WMI currently supports only the [CIM 2.x version schemas](Http://Go.Microsoft.Com/FWLink/p/?LinkID=309367).

�

The following syntax is simplified from Managed Object Format (MOF) code and includes all inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[Abstract, UUID("{A2EFC896-E3D3-11d2-8601-0000F8102E5F}"), AMENDMENT]
class CIM_ComputerSystemIRQ : CIM_ComputerSystemResource
{
  CIM_ComputerSystem REF GroupComponent;
  CIM_IRQ����������� REF PartComponent;
};
```

## Members

The **CIM\_ComputerSystemIRQ** class has these types of members:

-   [Properties](#properties)

### Properties

The **CIM\_ComputerSystemIRQ** class has these properties.

<dl> <dt>

**GroupComponent**
</dt> <dd> <dl> <dt>

Data type: **CIM\_ComputerSystem**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) (GroupComponent)
</dt> </dl>

A [**CIM\_ComputerSystem**](cim-computersystem.md) describing the computer associated with the IRQ.

This property is inherited from [**CIM\_ComputerSystemResource**](cim-computersystemresource.md)

</dd> <dt>

**PartComponent**
</dt> <dd> <dl> <dt>

Data type: **CIM\_IRQ**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**Override**](https://msdn.microsoft.com/library/aa393650) ("PartComponent"), [**Weak**](https://msdn.microsoft.com/library/aa393650)
</dt> </dl>

A [**CIM\_IRQ**](cim-irq.md) describing an IRQ of the computer system.

</dd> </dl>

## Remarks

The **CIM\_ComputerSystemIRQ** class is derived from [**CIM\_ComputerSystemResource**](cim-computersystemresource.md).

WMI does not implement this class.

This documentation is derived from the CIM class descriptions published by the DMTF. Microsoft may have made changes to correct minor errors, conform to Microsoft SDK documentation standards, or provide more information.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server�2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_ComputerSystemResource**](cim-computersystemresource.md)
</dt> </dl>

�

�



