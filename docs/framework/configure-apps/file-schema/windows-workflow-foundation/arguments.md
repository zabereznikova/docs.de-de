---
title: '&lt;Argumente&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: ae2fd4a05cc8ca93cd74ccceb08a7a077b504f0c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757410"
---
# <a name="ltargumentsgt"></a>&lt;Argumente&gt;
Stellt eine Auflistung von Argumenten dar, die einer Aktivitätszustandsabfrage zugeordnet sind.  
  
 Weitere Informationen zu nachverfolgungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
\<system.serviceModel>  
\<Nachverfolgen von >  
\<trackingProfile>  
\<Workflow >  
\<ActivityStateQueries >  
\<ActivityStateQuery >  
\<Argumente >  
  
## <a name="syntax"></a>Syntax  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
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
|[\<Argument >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|Ein einer Aktivitätszustandsabfrage zugeordnetes Argument.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|Stellt ein Konfigurationselement dar, das verwendet wird, um Anforderungen zum Abbrechen einer untergeordneten Aktivität durch die übergeordnete Aktivität nachzuverfolgen. Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Datensatzobjekte mit Abbruchanforderungen abonnieren kann.|  
  
## <a name="remarks"></a>Hinweise  
 Eine einzigartige Funktion des Elements „ActivityStateQuery“ ist seine Fähigkeit, Daten zu extrahieren, während es die Ausführung eines Workflows nachverfolgt. Dadurch steht zusätzlicher Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird. Können Sie die [ \<Argumente >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) und [ \<Zustände >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) Elemente, um alle Variablen oder Argumente zu extrahieren. aus einer beliebigen Aktivität in einem Workflow. Das folgende Beispiel zeigt eine Abfrage, die Variablen und Argumente extrahiert Status bei der Aktivitäts `Closed` Überwachungsdatensatz ausgegeben wird. Variablen und Argumente können nur mit einem ActivityStateRecord extrahiert werden und somit abonniert werden innerhalb eines Überwachungsprofils mit Profil [ \<ActivityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
