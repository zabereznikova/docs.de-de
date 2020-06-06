---
title: <behavior> von <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 115f94fc3f17dc5b4dd1ee3a090f2c9d121f810b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139736"
---
# <a name="behavior-of-servicebehaviors"></a>\<behavior> von \<serviceBehaviors>
Das `behavior`-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts. Jedes Verhalten wird durch seinen `name` indiziert. Dienste können mit dem-Attribut des-Elements über diesen Namen mit den einzelnen Verhalten verknüpft werden `behaviorConfiguration` [\<endpoint>](endpoint-element.md) . Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
> Verhaltenselemente, die für Windows Workflow-Aktivitäten spezifisch sind, z. b. das- [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) Element, werden auf der Seite [ \<behavior> von \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) dokumentiert.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|name|Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält. Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert. Ab .NET Framework 4 müssen Bindungen und Verhaltensweisen keinen Namen haben. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|Speichert die Konfigurationsinformationen für DataContractSerializer.|  
|[\<persistenceProvider>](persistenceprovider.md)|Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.|  
|[\<routing>](routing-of-servicebehavior.md)|Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.|  
|[\<serviceCredentials>](servicecredentials.md)|Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.|  
|[\<serviceDebug>](servicedebug.md)|Gibt Debugging-und Hilfe Informationsfunktionen für einen Windows Communication Foundation (WCF)-Dienst an.|  
|[\<serviceDiscovery>](servicediscovery.md)|Gibt die Ermittelbarkeit von Dienstendpunkten an.|  
|[\<serviceMetadata>](servicemetadata.md)|Gibt die Veröffentlichung der Dienstmetadaten und der zugeordneten Informationen an.|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|Legt Einstellungen fest, die die Überwachung von Sicherheitsereignissen während der Dienstvorgänge ermöglichen.|  
|[\<serviceThrottling>](servicethrottling.md)|Gibt den Drosselungs Mechanismus eines WCF-Dienstanbieter an.|  
|[\<serviceTimeouts>](servicetimeouts.md)|Gibt den Timeout für einen Dienst an.|  
|[\<workflowRuntime>](workflowruntime.md)|Gibt Einstellungen für eine Instanz von WorkflowRuntime zum Hosting Workflow basierter WCF-Dienste an.|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|Eine Auflistung von Dienstverhaltenselementen.|
