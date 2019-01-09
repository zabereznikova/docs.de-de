---
title: '&lt;state&gt; von WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 168a6980e955f602ee60bff26461f06cb16c836a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145925"
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a>&lt;state&gt; von WCF, &lt;workflowInstanceQuery&gt;
Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.  
  
 Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<Nachverfolgen von >  
\<Profile >  
\<trackingProfile>  
\<Workflow >  
\<workflowInstanceQueries>  
\<WorkflowInstanceQuery >  
\<Status >  
\<Status >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.
  
### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|  
|---------------|-----------------|  
|`name`|Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Status >](states-of-wcf-workflowinstancequery.md)|Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.|  
  
## <a name="remarks"></a>Hinweise  

Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.  
  
In der folgenden Tabelle werden die möglichen Statuswerte beschrieben:
  
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
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
