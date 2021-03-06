---
Description: Modifies the replication settings for a virtual machine. When a client calls this method for a replica virtual machine, it modifies the replication settings of the replication relationship with the extended replica.
ms.assetid: e68514a5-f508-4047-8dcc-6a95f3e3353e
title: ModifyReplicationSettings method of the Msvm_ReplicationService class
ms.topic: article
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- Msvm_ReplicationService.ModifyReplicationSettings
api_type: 
- COM
api_location: 
- vmms.exe
---

# ModifyReplicationSettings method of the Msvm\_ReplicationService class

Modifies the replication settings for a virtual machine. When a client calls this method for a replica virtual machine, it modifies the replication settings of the replication relationship with the extended replica.

## Syntax


```mof
uint32 ModifyReplicationSettings(
  [in]  CIM_ComputerSystem REF ComputerSystem,
  [in]  string                 ReplicationSettingData,
  [out] CIM_ConcreteJob    REF Job
);
```



## Parameters

<dl> <dt>

*ComputerSystem* \[in\]
</dt> <dd>

A reference to a [**CIM\_ComputerSystem**](https://docs.microsoft.com/windows/desktop/CIMWin32Prov/cim-computersystem) instance that represents the virtual machine for which the replication settings should be modified.

</dd> <dt>

*ReplicationSettingData* \[in\]
</dt> <dd>

A string representation of the [**Msvm\_ReplicationSettingData**](msvm-replicationsettingdata.md) class that defines the new replication settings.

</dd> <dt>

*Job* \[out\]
</dt> <dd>

If the operation is performed asynchronously, this method will return 4096, and this parameter will contain a reference to an object derived from [**CIM\_ConcreteJob**](https://docs.microsoft.com/previous-versions//cc136808(v=vs.85)).

</dd> </dl>

## Return value

This method returns one of the following values.

<dl> <dt>

**Completed with No Error** (0)
</dt> <dt>

**Method Parameters Checked - Job Started** (4096)
</dt> <dt>

**Failed** (32768)
</dt> <dt>

**Access Denied** (32769)
</dt> <dt>

**Not Supported** (32770)
</dt> <dt>

**Status is unknown** (32771)
</dt> <dt>

**Timeout** (32772)
</dt> <dt>

**Invalid parameter** (32773)
</dt> <dt>

**System is in use** (32774)
</dt> <dt>

**Invalid state for this operation** (32775)
</dt> <dt>

**Incorrect data type** (32776)
</dt> <dt>

**System is not available** (32777)
</dt> <dt>

**Out of memory** (32778)
</dt> <dt>

**File not found** (32779)
</dt> </dl>

## Remarks

**ModifyReplicationSettings** takes an [**Msvm\_ReplicationSettingData**](msvm-replicationsettingdata.md) instance (FRSD) as input. The associated FRSD for the virtual machine as host-to-host provider is the default choice. Input FRSD is validated for valid settings for each property for the default provider. This table summarizes the validation differences with respect to the external provider.



| Property                                             | External providers                                 |
|------------------------------------------------------|----------------------------------------------------|
| ReplicationProvider                                  | Same as default provider                           |
| AuthenticationType                                   | Ignored                                            |
| CertificateThumbPrint                                | Ignored                                            |
| RootCertificateThumbPrint (RO)                       | Ignored                                            |
| CompressionEnabled                                   | Same as default provider                           |
| BypassProxyServer                                    | Same as default provider                           |
| RecoveryConnectionPoint                              | Ignored\* (may change if provider has requirement) |
| RecoveryHostSystem (RO)                              | Ignored                                            |
| PrimaryConnectionPoint (RO)                          | Same as default provider                           |
| PrimaryHostSystem (RO)                               | Same as default provider                           |
| RecoveryServerPortNumber                             | Ignored\* (may change if provider has requirement) |
| ReplicateHostKvpItems                                | Ignored                                            |
| ApplicationConsistentSnapshotInterval                | Same as default provider                           |
| RecoveryHistory                                      | Same as default provider                           |
| IncludedDisks\[\]                                    | Same as default provider                           |
| AutoResynchronizeEnabled                             | Same as default provider                           |
| AutoResynchronizeIntervalStart                       | Same as default provider                           |
| AutoResynchronizeIntervalEnd                         | Same as default provider                           |
| EnableWriteOrderPreservationAcrossDisks (Deprecated) | Same as default provider                           |
| ReplicationInterval                                  | Same as default provider                           |



 

## Requirements



|                                     |                                                                                                         |
|-------------------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8 \[desktop apps only\]<br/>                                                              |
| Minimum supported server<br/> | Windows Server 2012 \[desktop apps only\]<br/>                                                    |
| Namespace<br/>                | Root\\Virtualization\\V2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Vmms.exe</dt> </dl>                     |



## See also

<dl> <dt>

[**Msvm\_ReplicationService**](msvm-replicationservice.md)
</dt> </dl>

 

 




