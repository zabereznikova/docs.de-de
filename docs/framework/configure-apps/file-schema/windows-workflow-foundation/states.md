---
title: "&lt;Zustände&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5e9050a01cf58c3c103fdbe4e8b22e173efaf5c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt"></a>&lt;Zustände&gt;
Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.  
  
 Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel >  
\<Nachverfolgen von >  
\<TrackingProfile >  
\<Workflow >  
\<WorkflowInstanceQueries >  
\<WorkflowInstanceQuery >  
\<Zustände >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<State >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<WorkflowInstanceQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.|  
  
## <a name="remarks"></a>Hinweise  
 Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.  
  
 Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.  
  
|Zustand|Beschreibung|  
|-----------|-----------------|  
|Aborted|Die Workflowinstanz wurde abgebrochen.|  
|Abgeschlossen|Die Workflowinstanz wurde abgeschlossen.|  
|Deleted|Die Workflowinstanz wurde gelöscht.|  
|Idle|Die Workflowinstanz ist im Leerlauf.|  
|Persisted|Die Workflowinstanz wurde beibehalten.|  
|Resumed|Die Workflowinstanz wurde wiederaufgenommen.|  
|Started|Die Workflowinstanz wurde gestartet.|  
|UnhandledException|In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.|  
|Unloaded|Die Workflowinstanz wurde entladen.|  
|Canceled|Die Workflowinstanz wurde abgebrochen.|  
|Angehalten|Die Workflowinstanz wurde unterbrochen.|  
|Terminated|Die Workflowinstanz wurde beendet.|  
|Unsuspended|Die Workflowinstanz wurde fortgesetzt.|  
  
## <a name="example"></a>Beispiel  
 In der folgende Konfiguration werden mithilfe einer Abfrage Workflownachverfolgungsdatensätze auf Instanzebene für den `Started`-Instanzzustand abonniert.  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
