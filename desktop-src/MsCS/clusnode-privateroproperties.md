---
title: ClusNode.PrivateROProperties property
description: Read-only private properties of a node.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: '146471dd-49f9-442c-a888-148fd86c4050'
ms.prod: 'windows-server-dev'
ms.technology: 'failover-clustering'
ms.tgt_platform: multiple
keywords: ["PrivateROProperties property Failover Cluster", "PrivateROProperties property Failover Cluster , ClusNode object", "ClusNode object Failover Cluster , PrivateROProperties property"]
topic_type:
- apiref
api_name:
- ClusNode.PrivateROProperties
api_location:
- MsClus.dll
api_type:
- COM
---

# ClusNode.PrivateROProperties property

\[The **PrivateROProperties** property is available for use in the operating systems specified in the Requirements section. It may be altered or unavailable in subsequent versions.\]

Returns the read-only [private properties](private-properties.md) of a [node](nodes.md).

This property is read-only.

## Syntax


```VB
ClusNode.PrivateROProperties
```



## Property value

A [**ClusProperties**](clusproperties-collection.md) collection to receive the read-only private properties of the node.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                             |
| Minimum supported server<br/> | Windows Server�2008 Enterprise, Windows Server�2008 Datacenter<br/>             |
| Header<br/>                   | <dl> <dt>MsClus.h</dt> </dl>   |
| IDL<br/>                      | <dl> <dt>MsClus.idl</dt> </dl> |
| Type library<br/>             | <dl> <dt>MsClus.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>MsClus.dll</dt> </dl> |
| IID<br/>                      | IID\_ISClusNode is defined as F2E606F8-2631-11D1-89F1-00A0C90D061E<br/>         |



## See also

<dl> <dt>

[**ClusNode**](clusnode-object.md)
</dt> <dt>

[**ClusProperties**](clusproperties-collection.md)
</dt> </dl>

�

�




