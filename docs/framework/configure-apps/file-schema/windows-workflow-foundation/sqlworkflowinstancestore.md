---
title: "&lt;sqlWorkflowInstanceStore&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;sqlWorkflowInstanceStore&gt;
Ein Dienstverhalten, das es ermöglicht, die Funktion <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> zu konfigurieren, die das Beibehalten von Zustandsinformationen für Workflowdienstinstanzen in einer SQL Server 2005\- oder SQL Server 2008\-Datenbank unterstützt.  Weitere Informationen zu diesem Feature finden Sie unter [SQL\-Workflowinstanzspeicher](../../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  
  
## Syntax  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <sqlWorkflowInstanceStore   
          connectionStringName=”String”   
          honstLockRenewalPeriod=”TimeSpan”  
          instanceCompletionAction=”DeleteNothing/DeleteAll”  
          instanceEncodingAction=”None/GZip”  
          instanceLockedExceptionAction=”NoRetry/BasicRetry/AggressiveRetry”  
          runnableInstancesDetectionPeriod=”TimeSpan” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|connectionString|Eine Zeichenfolge, die die Verbindungszeichenfolge enthält, mithilfe derer eine Verbindung mit einer zugrunde liegenden Persistenzdatenbank hergestellt wird.|  
|connectionStringName|Eine Zeichenfolge, die eine benannte Verbindungszeichenfolge zum Datenbankserver enthält.  Ein Beispiel für eine benannte Verbindungszeichenfolge ist "DefaultConnectionString".|  
|honstLockRenewalPeriod|Ein Timespan\-Wert, der den Zeitraum angibt, innerhalb dessen der Host die Sperre einer Instanz erneuern muss.  Wenn der Host die Sperre nicht im angegebenen Zeitraum erneuert, wird die Instanz entsperrt und möglicherweise von einem anderen Host aufgenommen.<br /><br /> Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird.  Ist dieses Attribut auf 0 \(null\) festgelegt, wird die Workflowinstanz sofort beibehalten und entladen, nachdem der Workflow in den Leerlauf versetzt wurde.  Der Entladevorgang wird deaktiviert, wenn dieses Attribut auf TimeSpan.MaxValue festgelegt wird.  Workflowinstanzen im Leerlauf werden nie entladen.|  
|instanceCompletionAction|Ein Wert, der angibt, ob Workflowinstanzdaten nach Abschluss der Workflowinstanz im persistenten Speicher verbleiben oder ob sie gelöscht werden.  Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Die aufgelisteten Aktionen bestehen aus dem Löschen oder Nichtlöschen der Instanzdaten aus dem Beibehaltungsspeicher beim Abschließen der Instanz.<br /><br /> Das Behalten von Instanzen nach Abschluss bewirkt, dass die Beibehaltungsdatenbank schnell wächst, was die Leistung der Datenbank beeinträchtigt.  Sie sollten eine Datenbanksäuberungsrichtlinie zum regelmäßigen Löschen dieser Datensätze konfigurieren, um sicherzustellen, dass die Leistung der Datenbank Ihren Leistungsanforderungen entspricht.|  
|instanceEncodingOption|Ein optionaler Wert, der angibt, ob die Instanzzustandsinformationen mit dem GZip\-Algorithmus komprimiert werden, bevor die Informationen im persistenten Speicher gespeichert werden.  Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceEncodingAction>.  Mögliche Werte für diese Eigenschaft sind "Keine" \(keine Komprimierung\) und "GZip" \(Komprimierung der Instanzdaten mit dem GZip\-Algorithmus\).|  
|instanceLockedExceptionAction|Ein Wert, der die Aktion angibt, die als Reaktion auf eine Ausnahme eintritt, die ausgelöst wird, wenn der Host versucht, eine Instanz zu sperren, während die Instanz schon von einem anderen Host gesperrt wurde.  Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Die für dieses Feld zugelassenen Optionen lauten: None, Basic Retry und Aggressive Retry.  Der Standardwert ist None.  Die folgende Liste enthält die Beschreibungen für diese drei Optionen:<br /><br /> -   Keine.  Der Diensthost versucht nicht, die Instanz zu sperren und übergibt die <xref:System.Runtime.Persistence.InstanceLockedException> an den Aufrufer.<br />-   Basic Retry.  Der Diensthost versucht erneut, die Instanz mit einem linearen Wiederholungsintervall zu sperren, und übergibt am Ende der Sequenz die Ausnahme an den Aufrufer.<br />-   Aggressive Retry.  Der Diensthost versucht erneut, die Instanz mit einer exponentiell zunehmenden Verzögerung zu sperren, und übergibt am Ende der Sequenz die <xref:System.Runtime.Persistence.InstanceLockedException> an den Aufrufer.|  
|runnableInstancesDetectionPeriod||  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<behavior\> von \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>   
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>   
 [SQL\-Workflowinstanzspeicher](../../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)