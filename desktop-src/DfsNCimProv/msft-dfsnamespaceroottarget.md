---
title: MSFT\_DfsNamespaceRootTarget class
description: Represents the target of a DFS namespace (DFS-N) root.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 'b6bcaacd-2055-47ad-8c35-81e50e68b0fb'
ms.prod: 'windows-server-dev'
ms.technology:
- 'distributed-file-system-namespace'
- 'windows-management-instrumentation'
ms.tgt_platform: multiple
keywords: ["MSFT_DfsNamespaceRootTarget class", "MSFT_DfsNamespaceRootTarget class, described"]
topic_type:
- apiref
api_name:
- MSFT_DfsNamespaceRootTarget
- MSFT_DfsNamespaceRootTarget.NamespacePath
- MSFT_DfsNamespaceRootTarget.ReferralPriorityClass
- MSFT_DfsNamespaceRootTarget.ReferralPriorityRank
- MSFT_DfsNamespaceRootTarget.State
- MSFT_DfsNamespaceRootTarget.TargetPath
api_location:
- DfsNCimProv.dll
api_type:
- DllExport
---

# MSFT\_DfsNamespaceRootTarget class

Represents the target of a DFS namespace (DFS-N) root.

The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.

## Syntax

``` syntax
[dynamic, provider("dfsncimprov"), ClassVersion("1.0"), AMENDMENT]
class MSFT_DfsNamespaceRootTarget : MSFT_DfsNamespaceTargetBase
{
  string NamespacePath;
  sint32 ReferralPriorityClass;
  uint32 ReferralPriorityRank;
  uint32 State;
  string TargetPath;
};
```

## Members

The **MSFT\_DfsNamespaceRootTarget** class has these types of members:

-   [Methods](#methods)
-   [Properties](#properties)

### Methods

The **MSFT\_DfsNamespaceRootTarget** class has these methods.



| Method                                                                                     | Description                                                                        |
|:-------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------|
| [**AddNamespaceRootTarget**](addnamespaceroottarget-msft-dfsnamespaceroottarget.md)       | Adds a new target for a DFS namespace (DFS-N) root.<br/>                     |
| [**GetNamespaceRootTarget**](getnamespaceroottarget-msft-dfsnamespaceroottarget.md)       | Retrieves the properties of the target of a DFS namespace (DFS-N) root.<br/> |
| [**RemoveNamespaceRootTarget**](removenamespaceroottarget-msft-dfsnamespaceroottarget.md) | Removes a target of a DFS namespace (DFS-N) root.<br/>                       |
| [**SetNamespaceRootTarget**](setnamespaceroottarget-msft-dfsnamespaceroottarget.md)       | Modifies the properties of the target of a DFS namespace (DFS-N) root.<br/>  |



�

### Properties

The **MSFT\_DfsNamespaceRootTarget** class has these properties.

<dl> <dt>

**NamespacePath**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157)
</dt> </dl>

Gets or sets the Universal Naming Convention (UNC) path of the DFS-N root or DFS-N link for which a target is to be created.

A DFS-N root or a DFS-N link can have one of the following UNC path formats:



|            | Server Format                     | Domain Format                     |
|------------|-----------------------------------|-----------------------------------|
| DFS-N Root | \\\\ServerName\\DFSName           | \\\\DomainName\\DFSName           |
| DFS-N Link | \\\\ServerName\\DFSName\\LinkPath | \\\\DomainName\\DFSName\\LinkPath |



�

where:

-   The ServerName component represents the host name of a DFS root target of a DFS namespace.
-   The DomainName component represents the domain name of the domain that hosts the domain-based DFS namespace.
-   The DFSName component represents the DFS-N name.
-   The LinkPath component represents the path of the DFS-N link relative to the DFS root target share.

Stand-alone DFS namespaces must have links and roots with the formats shown in the first column, as they must contain a server name. Domain-based DFS namespaces can have links and roots with the formats from either column, although the second column's formats (which contain a domain name instead of a server name) are the preferred format.

This property is inherited from [**MSFT\_DfsNamespaceTargetBase**](msft-dfsnamespacetargetbase.md).

</dd> <dt>

**ReferralPriorityClass**
</dt> <dd> <dl> <dt>

Data type: **sint32**
</dt> <dt>

Access type: Read-only
</dt> </dl>

Gets or sets the priority class of the DFS folder target. The default value is "Normal".

This property is inherited from [**MSFT\_DfsNamespaceTargetBase**](msft-dfsnamespacetargetbase.md).

<dt>

<span id="Invalid"></span><span id="invalid"></span><span id="INVALID"></span>

<span id="Invalid"></span><span id="invalid"></span><span id="INVALID"></span>**"Invalid"** (-1)


</dt> <dd>

Invalid priority.

</dd> <dt>

<span id="Normal"></span><span id="normal"></span><span id="NORMAL"></span>

<span id="Normal"></span><span id="normal"></span><span id="NORMAL"></span>**"Normal"** (0)


</dt> <dd>

Site cost, normal priority.

</dd> <dt>

<span id="global-high"></span><span id="GLOBAL-HIGH"></span>

<span id="global-high"></span><span id="GLOBAL-HIGH"></span>**"global-high"** (1)


</dt> <dd>

Global, high priority.

</dd> <dt>

<span id="sitecost-high"></span><span id="SITECOST-HIGH"></span>

<span id="sitecost-high"></span><span id="SITECOST-HIGH"></span>**"sitecost-high"** (2)


</dt> <dd>

Site cost, high priority.

</dd> <dt>

<span id="sitecost-low"></span><span id="SITECOST-LOW"></span>

<span id="sitecost-low"></span><span id="SITECOST-LOW"></span>**"sitecost-low"** (3)


</dt> <dd>

Site cost, low priority.

</dd> <dt>

<span id="global-low"></span><span id="GLOBAL-LOW"></span>

<span id="global-low"></span><span id="GLOBAL-LOW"></span>**"global-low"** (4)


</dt> <dd>

Global, low priority.

</dd> </dl>

</dd> <dt>

**ReferralPriorityRank**
</dt> <dd> <dl> <dt>

Data type: **uint32**
</dt> <dt>

Access type: Read-only
</dt> </dl>

Gets or sets the priority rank of the DFS folder target. The default value is 0.

This property is inherited from [**MSFT\_DfsNamespaceTargetBase**](msft-dfsnamespacetargetbase.md).

</dd> <dt>

**State**
</dt> <dd> <dl> <dt>

Data type: **uint32**
</dt> <dt>

Access type: Read-only
</dt> </dl>

Gets or sets the state of the DFS namespace folder target. The default value is "ONLINE".

This property is inherited from [**MSFT\_DfsNamespaceTargetBase**](msft-dfsnamespacetargetbase.md).

<dt>

<span id="OFFLINE"></span><span id="offline"></span>

<span id="OFFLINE"></span><span id="offline"></span>**"OFFLINE"** (3)


</dt> <dd>

Not online. Referrals are disabled.

</dd> <dt>

<span id="ONLINE"></span><span id="online"></span>

<span id="ONLINE"></span><span id="online"></span>**"ONLINE"** (4)


</dt> <dd>

Online. Referrals are enabled.

</dd> </dl>

</dd> <dt>

**TargetPath**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157)
</dt> </dl>

Gets or sets the UNC path of the target of a DFS-N root or a DFS-N link.

The DFS-N root target has a format of \\\\*ServerName*\\*ShareName*, where the *ServerName* component is the host name of a DFS-N root target server, and the *ShareName* component is the share name corresponding to a namespace on the DFS-N root target server.

The DFS-N link target has a format of \\\\*HostName*\\*SharedName*\[\\*ObjectName*\]\*, where:

-   The *HostName* component represents either the host name of a server or the domain name of a domain that hosts resources.
-   The *SharedName* component represents the share name or the name of the resource that is being accessed.
-   Each *ObjectName* component represents the name of a directory on the resource that is being accessed.

This property is inherited from [**MSFT\_DfsNamespaceTargetBase**](msft-dfsnamespacetargetbase.md).

</dd> </dl>

## Requirements



|                                     |                                                                                            |
|-------------------------------------|--------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                  |
| Minimum supported server<br/> | Windows Server�2012<br/>                                                             |
| Namespace<br/>                | Root\\Microsoft\\Windows\\dfsn<br/>                                                  |
| MOF<br/>                      | <dl> <dt>DfsNCimProv.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>DfsNCimProv.dll</dt> </dl> |



�

�




