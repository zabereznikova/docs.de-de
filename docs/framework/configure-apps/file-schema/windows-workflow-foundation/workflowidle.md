---
title: '&lt;workflowIdle&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 65bcc1ccd357fb7f331665aefbd975b11a2378cd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
Ein Dienstverhalten, das steuert, wann Workflowinstanzen im Leerlauf entladen und beibehalten werden.  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<WorkflowIdle >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|timeToPersist|Ein Timespan-Wert, der die Dauer zwischen dem Zeitpunkt angibt, der Workflow in den Leerlauf und wird beibehalten. Der Standardwert ist TimeSpan.MaxValue an.<br /><br /> Der Zeitraum beginnt abzulaufen, sobald die Workflowinstanz in den Leerlauf versetzt wird. Dieses Attribut ist hilfreich, wenn eine Workflowinstanz, die genauer gleichzeitig die Instanz für solange wie möglich im Arbeitsspeicher beibehalten werden sollen. Dieses Attribut ist nur gültig, wenn der Wert ist kleiner als das **TimeToUnload** Attribut. Ist er größer, wird das Attribut ignoriert. Wenn dieses Attribut, bevor der Wert verstreicht von der **TimeToUnload** -Attribut, Persistenz muss abgeschlossen werden, bevor der Workflow entladen wird. Dies bedeutet, dass der Entladevorgang möglicherweise verzögert wird, bis der Workflow beibehalten wird. Die Beibehaltungsebene ist für das Behandeln von Wiederholungen für flüchtige Fehler zuständig und löst nur bei nicht behebbaren Fehlern Ausnahmen aus. Daher werden alle während der Beibehaltung ausgelöste Ausnahmen als schwerwiegend behandelt, und die Workflowinstanz wird abgebrochen.|  
|timeToUnload|Ein Timespan-Wert, der den Zeitraum angibt, nach dessen Ablauf ein im Leerlauf befindlicher Workflow entladen wird. Der Standardwert beträgt 1 Minute.<br /><br /> Einen Workflow zu entladen impliziert, dass dieser auch beibehalten wird. Wenn dieses Attribut auf 0 (null) festgelegt ist, die Workflowinstanz beibehalten und entladen, unmittelbar nach, wird der Workflow im Leerlauf. Durch Festlegen dieses Attributs auf TimeSpan.MaxValue effektiv deaktiviert der Entladevorgang. Workflowinstanzen im Leerlauf werden nie entladen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten > der \<ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
