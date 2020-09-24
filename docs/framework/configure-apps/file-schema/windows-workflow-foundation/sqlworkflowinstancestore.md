---
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: d6c86d02e14a38c2a35ba4858c4abfea73268fd8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148710"
---
# \<sqlWorkflowInstanceStore>

Ein Dienstverhalten, das es ermöglicht, die Funktion <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> zu konfigurieren, die das Beibehalten von Zustandsinformationen für Workflowdienstinstanzen in eine SQL Server 2005- oder SQL Server 2008-Datenbank unterstützt. Weitere Informationen zu diesem Feature finden Sie unter [SQL-workflowinstanzspeicher](../../../windows-workflow-foundation/sql-workflow-instance-store.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sqlWorkflowInstanceStore>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String"
                                hostLockRenewalPeriod="TimeSpan"
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
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|connectionString|Eine Zeichenfolge, die die Verbindungszeichenfolge enthält, mithilfe derer eine Verbindung mit einer zugrunde liegenden Persistenzdatenbank hergestellt wird.|  
|connectionStringName|Eine Zeichenfolge, die eine benannte Verbindungszeichenfolge zum Datenbankserver enthält. Ein Beispiel für eine benannte Verbindungs Zeichenfolge ist "defaultconnectionstring".|  
|hostlockrenewalperiod|Ein Timespan-Wert, der den Zeitraum angibt, innerhalb dessen der Host die Sperre einer Instanz erneuern muss. Wenn der Host die Sperre nicht im angegebenen Zeitraum erneuert, wird die Instanz entsperrt und möglicherweise von einem anderen Host aufgenommen.<br /><br /> Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird. Ist dieses Attribut auf 0 (null) festgelegt, wird die Workflowinstanz sofort beibehalten und entladen, nachdem der Workflow in den Leerlauf versetzt wurde. Der Entladevorgang wird deaktiviert, wenn dieses Attribut auf TimeSpan.MaxValue festgelegt wird. Workflowinstanzen im Leerlauf werden nie entladen.|  
|instanceCompletionAction|Ein Wert, der angibt, ob Workflowinstanzdaten nach Abschluss der Workflowinstanz im persistenten Speicher verbleiben oder ob sie gelöscht werden. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Die aufgelisteten Aktionen bestehen aus dem Löschen oder Nichtlöschen der Instanzdaten aus dem Beibehaltungsspeicher beim Abschließen der Instanz.<br /><br /> Das Behalten von Instanzen nach Abschluss bewirkt, dass die Beibehaltungsdatenbank schnell wächst, was die Leistung der Datenbank beeinträchtigt. Sie sollten eine Datenbanksäuberungsrichtlinie zum regelmäßigen Löschen dieser Datensätze konfigurieren, um sicherzustellen, dass die Leistung der Datenbank Ihren Leistungsanforderungen entspricht.|  
|instanceEncodingOption|Ein optionaler Wert, der angibt, ob die Instanzzustandsinformationen mit dem GZip-Algorithmus komprimiert werden, bevor die Informationen im persistenten Speicher gespeichert werden. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceEncodingOption>. Mögliche Werte für diese Eigenschaft sind <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None> , die keine Komprimierung angibt, und <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip> , der angibt, dass Instanzdaten komprimiert werden und den gzip-Algorithmus verwenden.|  
|instanceLockedExceptionAction|Ein Wert, der die Aktion angibt, die als Reaktion auf eine Ausnahme eintritt, die ausgelöst wird, wenn der Host versucht, eine Instanz zu sperren, während die Instanz schon von einem anderen Host gesperrt wurde. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Die für dieses Feld zugelassenen Optionen lauten: None, Basic Retry und Aggressive Retry. Der Standardwert lautet „Keine“. Die folgende Liste enthält die Beschreibungen für diese drei Optionen:<br /><br /> –  Keine. Der Diensthost versucht nicht, die Instanz zu sperren und übergibt die <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer.<br />-Grundlegende Wiederholung. Der Diensthost versucht erneut, die Instanz mit einem linearen Wiederholungsintervall zu sperren, und übergibt am Ende der Sequenz die Ausnahme an den Aufrufer.<br />-Aggressive Wiederholung. Der Diensthost versucht erneut, die Instanz mit einer exponentiell zunehmenden Verzögerung zu sperren, und übergibt am Ende der Sequenz die <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior> von \<serviceBehaviors>](behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [SQL-Workflowinstanzspeicher](../../../windows-workflow-foundation/sql-workflow-instance-store.md)
