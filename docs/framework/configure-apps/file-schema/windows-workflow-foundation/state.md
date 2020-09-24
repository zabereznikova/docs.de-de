---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 169fa900b5be9a9577818b68b540184afd4a6681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169725"
---
# \<state>

Stellt bei der Erstellung von Nachverfolgungsdatensätzen eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz dar.  
  
 Weitere Informationen zu Überwachungs Profil Abfragen finden Sie unter nach [Verfolgungs profile](../../../windows-workflow-foundation/tracking-profiles.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<tracking>
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
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|name|Eine Zeichenfolge, die bei der Erstellung eines Nachverfolgungsdatensatzes einen abonnierten Zustand der nachverfolgten Workflowinstanz angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<states>](states.md)|Eine Auflistung abonnierter Zustände der nachverfolgten Workflowinstanz bei der Erstellung von Nachverfolgungsdatensätzen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Die zurückgegebenen Datensätze werden entsprechend den Zuständen in dieser Auflistung gefiltert.  
  
 Eine Beschreibung der möglichen Zustandswerte finden Sie in der folgenden Tabelle.  
  
|State|BESCHREIBUNG|  
|-----------|-----------------|  
|Aborted|Die Workflowinstanz wurde abgebrochen.|  
|Abgeschlossen|Die Workflowinstanz wurde abgeschlossen.|  
|Deleted|Die Workflowinstanz wurde gelöscht.|  
|Idle|Die Workflowinstanz ist im Leerlauf.|  
|Persistent|Die Workflowinstanz wurde beibehalten.|  
|Resumed|Die Workflowinstanz wurde wiederaufgenommen.|  
|Gestartet|Die Workflowinstanz wurde gestartet.|  
|UnhandledException|In der Workflowinstanz ist eine nicht behandelte Ausnahme aufgetreten.|  
|Nicht Geladen|Die Workflowinstanz wurde entladen.|  
|Canceled|Die Workflowinstanz wurde abgebrochen.|  
|Ausgesetzt|Die Workflowinstanz wurde unterbrochen.|  
|Beendet|Die Workflowinstanz wurde beendet.|  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Nachverfolgung und Ablaufverfolgung für Workflows](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Überwachungsprofile](../../../windows-workflow-foundation/tracking-profiles.md)
