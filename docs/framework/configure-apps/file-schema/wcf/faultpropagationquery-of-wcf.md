---
title: '&lt;faultPropagationQuery&gt; von WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: c3853c470a9243835e071d35008dfff5b885591d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123318"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a>&lt;faultPropagationQuery&gt; von WCF

Stellt eine Abfrage dar, die verwendet wird, um die Behandlung von Fehlern zu verfolgen, die in einer Aktivität auftreten.  Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet. Sie sollten eine solche Abfrage verwenden, um die Behandlung der Fehler nachzuverfolgen, die in einer Aktivität auftreten. Die Abfrage ist notwendig, damit ein Nachverfolgungsteilnehmer Fehlerbehandlungsdatensätze abonnieren kann.  
  
Weitere Informationen zu überwachungsprofilabfragen finden Sie unter [Nachverfolgungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
\<system.serviceModel>  
\<Nachverfolgen von >  
\<Profile >  
\<trackingProfile>  
\<Workflow >  
\<FaultPropagationQueries >  
\<FaultPropagationQuery >  
  
## <a name="syntax"></a>Syntax  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
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
|`faultSourceActivityName`|Eine Zeichenfolge, die den Namen der FaultHandler-Aktivität angibt, die den Fehler weitergegeben hat. Der Standardwert ist \*, was bedeutet, dass für alle Aktivitäten fehlerweitergabedatensätze zurückgegeben werden.|  
|`faultHandlerActivityName`|Eine Zeichenfolge, die den Namen der Aktivität angibt, in der der Fehler aufgetreten ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente

Keine
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|Stellt eine Liste von Konfigurationselementen dar, die verwendet werden, um die Behandlung der Fehler zu verfolgen, die in einer Aktivität auftreten.  Dieses Ereignis tritt jedes Mal auf, wenn ein FaultHandler einen Fehler verarbeitet.|
  
## <a name="see-also"></a>Siehe auch  
 
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [Nachverfolgung und Ablaufverfolgung für Workflows](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Überwachungsprofile](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
