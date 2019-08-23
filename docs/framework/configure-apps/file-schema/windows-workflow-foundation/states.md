---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: fd0b57d7d08cf77ba7792e079b7abd2ff8f2839e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947404"
---
# <a name="states"></a>\<Status >
Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.  
  
 Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .  
  
\<system.serviceModel>  
\<Überwachungs >  
\<trackingProfile>  
\<workflow>  
\<workflowInstanceQueries>  
\<workflowInstanceQuery>  
\<Status >  
  
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
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<state>](states.md)|Ein abonnierter Zustand der verfolgten Workflowinstanz, wenn der Nachverfolgungsdatensatz erstellt wird.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|Eine Abfrage, die Änderungen im Lebenszyklus einer Workflowinstanz nachverfolgt, beispielsweise ein gestartetes oder abgeschlossenes Ereignis.|  
  
## <a name="remarks"></a>Hinweise  
 Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.  
  
 Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.  
  
|Status|Beschreibung|  
|-----------|-----------------|  
|Aborted|Die Workflowinstanz wurde abgebrochen.|  
|Abgeschlossen|Die Workflowinstanz wurde abgeschlossen.|  
|Deleted|Die Workflowinstanz wurde gelöscht.|  
|Idle|Die Workflowinstanz ist im Leerlauf.|  
|Persisted|Die Workflowinstanz wurde beibehalten.|  
|Resumed|Die Workflowinstanz wurde wiederaufgenommen.|  
|Started|Die Workflowinstanz wurde gestartet.|  
|UnhandledException|In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.|  
|Nicht Geladen|Die Workflowinstanz wurde entladen.|  
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

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Nachverfolgung und Ablaufverfolgung für Workflows](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Überwachungsprofile](../../../windows-workflow-foundation/tracking-profiles.md)
