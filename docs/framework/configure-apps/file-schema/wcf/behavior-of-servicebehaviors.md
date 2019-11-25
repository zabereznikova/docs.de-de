---
title: <behavior> von <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 115f94fc3f17dc5b4dd1ee3a090f2c9d121f810b
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139736"
---
# <a name="behavior-of-servicebehaviors"></a>\<Verhalten > von \<Service Behavior >
Das `behavior`-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts. Jedes Verhalten wird durch seinen `name` indiziert. Dienste können mithilfe des `behaviorConfiguration`-Attributs des [\<Endpoint >](endpoint-element.md) -Elements mit den einzelnen Verhalten verknüpft werden. Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
> Verhaltenselemente, die spezifisch für Windows Workflow-Aktivitäten sind, wie z. b. das [\<SendMessageChannelCache->](../windows-workflow-foundation/sendmessagechannelcache.md) Element, werden im [\<Verhalten > der \<Seite > serviceverhaltensweisen](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) dokumentiert.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhalten**](behaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**serviceverhaltensweisen**](servicebehaviors.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Verhalten >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält. Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<DataContractSerializer >](datacontractserializer-element.md)|Speichert die Konfigurationsinformationen für DataContractSerializer.|  
|[\<PersistenceProvider >](persistenceprovider.md)|Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.|  
|[\<Routing >](routing-of-servicebehavior.md)|Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.|  
|[\<serviceauthenticationmanager >](serviceauthenticationmanager.md)|Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.|  
|[\<ServiceAuthorization >](serviceauthorization-element.md)|Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.|  
|[\<servicecreden->](servicecredentials.md)|Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.|  
|[\<serviceDebug->](servicedebug.md)|Gibt Debugging-und Hilfe Informationsfunktionen für einen Windows Communication Foundation (WCF)-Dienst an.|  
|[\<Service Discovery >](servicediscovery.md)|Gibt die Ermittelbarkeit von Dienstendpunkten an.|  
|[\<serviceMetadata >](servicemetadata.md)|Gibt die Veröffentlichung der Dienstmetadaten und der zugeordneten Informationen an.|  
|[\<serviceSecurityAudit >](servicesecurityaudit.md)|Legt Einstellungen fest, die die Überwachung von Sicherheitsereignissen während der Dienstvorgänge ermöglichen.|  
|[\<servicedrosselungs >](servicethrottling.md)|Gibt den Drosselungs Mechanismus eines WCF-Dienstanbieter an.|  
|[\<servicetimeouts >](servicetimeouts.md)|Gibt den Timeout für einen Dienst an.|  
|[\<WorkflowRuntime->](workflowruntime.md)|Gibt Einstellungen für eine Instanz von WorkflowRuntime zum Hosting Workflow basierter WCF-Dienste an.|  
|[\<useRequestHeadersForMetadataAddress >](userequestheadersformetadataaddress.md)|Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceverhaltens>](servicebehaviors.md)|Eine Auflistung von Dienstverhaltenselementen.|
