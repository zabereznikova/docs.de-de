---
title: "&lt;states&gt; von &lt;activityStateQuery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;states&gt; von &lt;activityStateQuery&gt;
Eine Auflistung von Konfigurationselementen, die die Zustände der abonnierten Aktivität enthalten, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.  
  
 Weitere Informationen zu Nachverfolgungsprofilabfragen finden Sie unter [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Syntax  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <activityStateQueries>  
             <activityStateQuery activityName="String" />  
                <states>  
                   <state name="String"/>  
                </states>  
          </activityStateQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<state\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|Ein Konfigurationselement, das die Zustände der abonnierten Aktivität enthält, für die ein Nachverfolgungsdatensatz ausgegeben werden soll.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen.  Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.|  
  
## Hinweise  
 Eine einzigartige Funktion des ActivityStateQuery\-Elements ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt.  Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.  Sie können mit den Elementen [\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) jede beliebige Variable oder jedes beliebige Argument aus einer beliebigen Aktivität in einem Workflow extrahieren. Das folgende Beispiel zeigt eine Aktivitätszustandsabfrage, die Variablen und Argumente extrahiert, wenn der `Closed`\-Nachverfolgungsdatensatz der Aktivität ausgegeben wird.  Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und werden daher innerhalb eines Nachverfolgungsprofils mit [\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md) abonniert.  
  
```  
  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
  
```  
  
## Siehe auch  
 [System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection](assetId:///System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityStateQuery](assetId:///System.Activities.Tracking.ActivityStateQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)