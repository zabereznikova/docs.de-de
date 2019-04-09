---
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 8601f1c7f4e1dbf911020c328652c371bf039124
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119079"
---
# <a name="sqlworkflowinstancestore"></a>\<sqlWorkflowInstanceStore>
Ein Dienstverhalten, das Sie konfigurieren kann die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> -Funktion, die beibehalten von Zustandsinformationen für workflowdienstinstanzen in eine SQL Server 2005 oder SQL Server 2008-Datenbank unterstützt. Weitere Informationen zu diesem Feature finden Sie unter [SQL Workflow-Instanz Store](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<sqlWorkflowInstanceStore>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                honstLockRenewalPeriod="TimeSpan" 
                                instanceCompletionAction="DeleteNothing/DeleteAll" 
                                instanceEncodingAction="None/GZip" 
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|connectionString|Eine Zeichenfolge, die eine Verbindungszeichenfolge zur Verbindung mit einer zugrunde liegenden beibehaltungsdatenbank enthält.|  
|connectionStringName|Eine Zeichenfolge, die eine benannte Verbindungszeichenfolge zum Datenbankserver enthält. Ein Beispiel für eine benannte Verbindungszeichenfolge ist "DefaultConnectionString".|  
|honstLockRenewalPeriod|Ein Timespan-Wert, der den Zeitraum angibt, innerhalb dessen der Host die Sperre einer Instanz erneuern muss. Wenn der Host die Sperre nicht im angegebenen Zeitraum erneuert, wird die Instanz entsperrt und möglicherweise von einem anderen Host aufgenommen.<br /><br /> Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird. Wenn dieses Attribut auf 0 (null) festgelegt ist, die Workflowinstanz beibehalten und entladen, unmittelbar, in den Leerlauf des Workflows. Wenn dieses Attribut auf TimeSpan.MaxValue festgelegt effektiv deaktiviert der Entladevorgang. Workflowinstanzen im Leerlauf werden nie entladen.|  
|instanceCompletionAction|Ein Wert, der angibt, ob Workflowinstanzdaten nach Abschluss der Workflowinstanz im persistenten Speicher verbleiben oder ob sie gelöscht werden. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Die aufgelisteten Aktionen bestehen aus dem Löschen oder Nichtlöschen der Instanzdaten aus dem Beibehaltungsspeicher beim Abschließen der Instanz.<br /><br /> Das Behalten von Instanzen nach Abschluss bewirkt, dass die Beibehaltungsdatenbank schnell wächst, was die Leistung der Datenbank beeinträchtigt. Sie sollten eine Datenbanksäuberungsrichtlinie zum regelmäßigen Löschen dieser Datensätze konfigurieren, um sicherzustellen, dass die Leistung der Datenbank Ihren Leistungsanforderungen entspricht.|  
|instanceEncodingOption|Ein optionaler Wert, der angibt, ob die Instanzzustandsinformationen mit dem GZip-Algorithmus komprimiert werden, bevor die Informationen im persistenten Speicher gespeichert werden. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceEncodingOption>. Mögliche Werte für diese Eigenschaft sind <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None>, der angibt, dass keine Komprimierung und <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip>, der angibt, dass die Instanzdaten komprimiert werden, und verwendet den Gzip-Algorithmus.|  
|instanceLockedExceptionAction|Ein Wert, der die Aktion angibt, die als Reaktion auf eine Ausnahme eintritt, die ausgelöst wird, wenn der Host versucht, eine Instanz zu sperren, während die Instanz schon von einem anderen Host gesperrt wurde. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Die für dieses Feld zugelassenen Optionen sind: None, Basic Retry und Aggressive Retry. Der Standardwert ist None. Die folgende Liste enthält die Beschreibungen für diese drei Optionen:<br /><br /> –  Keine. Der Diensthost versucht nicht, die Instanz zu sperren und übergibt die <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer.<br />-Einfache Wiederholung. Der Diensthost versucht erneut, die Instanz mit einem linearen Wiederholungsintervall zu sperren, und übergibt am Ende der Sequenz die Ausnahme an den Aufrufer.<br />-Aggressive Retry. Der Diensthost versucht erneut, die Instanz mit einer exponentiell zunehmenden Verzögerung zu sperren, und übergibt am Ende der Sequenz die <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten > der \<ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [SQL-Workflowinstanzspeicher](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
