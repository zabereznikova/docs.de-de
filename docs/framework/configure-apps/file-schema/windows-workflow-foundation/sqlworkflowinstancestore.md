---
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 581da860a490c95d5d621194c7f6643fc15118fe
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398683"
---
# <a name="sqlworkflowinstancestore"></a>\<sqlWorkflowInstanceStore>
Ein Dienst Verhalten, mit dem Sie die <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Funktion konfigurieren können, die das Beibehalten von Zustandsinformationen für Workflow Dienst Instanzen in eine SQL Server 2005-oder SQL Server 2008-Datenbank unterstützt. Weitere Informationen zu diesem Feature finden Sie unter [SQL-workflowinstanzspeicher](../../../windows-workflow-foundation/sql-workflow-instance-store.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Anlage. Service Model->** ](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<SqlWorkflowInstanceStore >**  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|connectionString|Eine Zeichenfolge mit einer Verbindungs Zeichenfolge zum Herstellen einer Verbindung mit einer zugrunde liegenden Persistenzdatenbank.|  
|connectionStringName|Eine Zeichenfolge, die eine benannte Verbindungs Zeichenfolge für den Datenbankserver enthält. Ein Beispiel für eine benannte Verbindungs Zeichenfolge ist "defaultconnectionstring".|  
|hostLockRenewalPeriod|Ein Timespan-Wert, der den Zeitraum angibt, innerhalb dessen der Host die Sperre einer Instanz erneuern muss. Wenn der Host die Sperre nicht im angegebenen Zeitraum erneuert, wird die Instanz entsperrt und möglicherweise von einem anderen Host aufgenommen.<br /><br /> Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird. Wenn dieses Attribut auf 0 (null) festgelegt ist, wird die Workflow Instanz permanent gespeichert und entladen, sobald der Workflow in den Leerlauf wechselt. Wenn dieses Attribut auf TimeSpan. MaxValue festgelegt wird, wird der Entladevorgang effektiv deaktiviert. Workflowinstanzen im Leerlauf werden nie entladen.|  
|instanceCompletionAction|Ein Wert, der angibt, ob Workflowinstanzdaten nach Abschluss der Workflowinstanz im persistenten Speicher verbleiben oder ob sie gelöscht werden. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Die aufgelisteten Aktionen bestehen aus dem Löschen oder Nichtlöschen der Instanzdaten aus dem Beibehaltungsspeicher beim Abschließen der Instanz.<br /><br /> Das Behalten von Instanzen nach Abschluss bewirkt, dass die Beibehaltungsdatenbank schnell wächst, was die Leistung der Datenbank beeinträchtigt. Sie sollten eine Datenbanksäuberungsrichtlinie zum regelmäßigen Löschen dieser Datensätze konfigurieren, um sicherzustellen, dass die Leistung der Datenbank Ihren Leistungsanforderungen entspricht.|  
|instanceEncodingOption|Ein optionaler Wert, der angibt, ob die Instanzzustandsinformationen mit dem GZip-Algorithmus komprimiert werden, bevor die Informationen im persistenten Speicher gespeichert werden. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceEncodingOption>. Mögliche Werte für diese Eigenschaft sind <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None>, die keine Komprimierung angibt, <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip>und, der angibt, dass Instanzdaten komprimiert werden und den gzip-Algorithmus verwenden.|  
|instanceLockedExceptionAction|Ein Wert, der die Aktion angibt, die als Reaktion auf eine Ausnahme eintritt, die ausgelöst wird, wenn der Host versucht, eine Instanz zu sperren, während die Instanz schon von einem anderen Host gesperrt wurde. Dieser Wert ist vom Typ <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Folgende Optionen sind für dieses Feld zulässig: Keine, einfache Wiederholung und aggressiver Wiederholungsversuch. Der Standardwert ist None. Die folgende Liste enthält die Beschreibungen für diese drei Optionen:<br /><br /> –  Keine. Der Diensthost versucht nicht, die Instanz zu sperren und übergibt die <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer.<br />-Grundlegende Wiederholung. Der Diensthost versucht erneut, die Instanz mit einem linearen Wiederholungsintervall zu sperren, und übergibt am Ende der Sequenz die Ausnahme an den Aufrufer.<br />-Aggressive Wiederholung. Der Diensthost versucht erneut, die Instanz mit einer exponentiell zunehmenden Verzögerung zu sperren, und übergibt am Ende der Sequenz die <xref:System.Runtime.DurableInstancing.InstanceLockedException> an den Aufrufer.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhaltens > von \<ServiceBehavior >](behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [SQL-Workflowinstanzspeicher](../../../windows-workflow-foundation/sql-workflow-instance-store.md)
