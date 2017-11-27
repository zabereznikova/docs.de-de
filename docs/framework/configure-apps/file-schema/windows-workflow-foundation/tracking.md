---
title: '&lt;Nachverfolgen&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7a03f3ca7159cd6e7b402bafd421cfee1a1d56d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lttrackinggt"></a>&lt;Nachverfolgen&gt;
Stellt einen Konfigurationsabschnitt zum Definieren von Nachverfolgungseinstellungen für einen Workflowdienst dar.  
  
 Weitere Informationen workflownachverfolgung und zur Konfiguration finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) und [Konfigurieren der nachverfolgung für einen Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).  
  
\<system.serviceModel >  
\<Nachverfolgen von >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Teilnehmer >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|Eine Auflistung von Konfigurationselementen, die Teilnehmer angibt, die Nachverfolgungsdatensätze abonnieren. Die Nachverfolgungsteilnehmer enthalten die Logik zur Verarbeitung der Nutzdaten der Nachverfolgungsdatensätze (beispielsweise für das Schreiben in eine Datei).|  
|[\<TrackingProfile >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|Ein Nachverfolgungsprofil, das die von einer Workflowinstanz ausgegebenen Nachverfolgungsdatensätze filtert.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|system.ServiceModel|Das Stammelement aller Workflow-Konfigurationselemente.|  
  
## <a name="remarks"></a>Hinweise  
 Die Nachverfolgung bietet Ihnen die Möglichkeit, die Ausführung eines Workflows zu untersuchen. Die Infrastruktur für die Workflownachverfolgung verwendet einen Workflow, um während der Ausführung Datensätze auszugeben, die Schlüsselereignisse festhalten. Nachverfolgungsdatensätze werden zum Beispiel ausgegeben, wenn eine Workflowinstanz startet oder abgeschlossen wird. Die Nachverfolgung kann auch geschäftsrelevante, den Workflowvariablen zugeordnete Daten extrahieren. Wenn zum Beispiel der Workflow ein System zur Verarbeitung von Bestellungen darstellt, kann die Bestellungs-ID zusammen mit dem Nachverfolgungsdatensatz extrahiert werden. Im Allgemeinen erleichtert die WF-Nachverfolgung während einer Workflowausführung die Diagnose oder die Geschäftsanalyse.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>       
 [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
