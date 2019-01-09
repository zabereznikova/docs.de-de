---
title: '&lt;behavior&gt; von &lt;serviceBehaviors&gt;'
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 2c6d477229a7c8a9b18ad6819bad1ad9f19696ac
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146887"
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt"></a>&lt;behavior&gt; von &lt;serviceBehaviors&gt;
Das `behavior`-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Diensts. Jedes Verhalten wird durch seinen `name` indiziert. Dienste können eine Verknüpfung mit jedem Verhalten über diesen Namen über die `behaviorConfiguration` Attribut der [ \<Endpunkt >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Element. Dies ermöglicht es Endpunkten, allgemeine Verhaltenskonfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
>  Windows Workflow-Aktivitäten spezifische verhaltenselemente wie z. B. die [ \<sendmessagechannelcache an >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md) Element werden dokumentiert die [ \<Verhalten > der \< ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) Seite.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
  
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
|Name|Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält. Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|Speichert die Konfigurationsinformationen für DataContractSerializer.|  
|[\<PersistenceProvider >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.|  
|[\<Routing >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Bietet Laufzeitzugriff auf den Routingdienst, um eine dynamische Änderung der Routingkonfiguration zu ermöglichen.|  
|[\<ServiceAuthenticationManager >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.|  
|[\<ServiceAuthorization >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|Gibt Einstellungen an, die den Zugriff auf Dienstvorgänge autorisieren.|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.|  
|[\<ServiceDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|Gibt Debugging- und hilfeinformationsfunktionen für einen Windows Communication Foundation (WCF)-Dienst.|  
|[\<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|Gibt die Ermittelbarkeit von Dienstendpunkten an.|  
|[\<ServiceMetadata >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|Gibt die Veröffentlichung der Dienstmetadaten und der zugeordneten Informationen an.|  
|[\<ServiceSecurityAudit >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|Legt Einstellungen fest, die die Überwachung von Sicherheitsereignissen während der Dienstvorgänge ermöglichen.|  
|[\<ServiceThrottling >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|Gibt den Einschränkungsmechanismus eines WCF-Diensts an.|  
|[\<ServiceTimeouts >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|Gibt den Timeout für einen Dienst an.|  
|[\<workflowRuntime>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Gibt Einstellungen für eine Instanz von WorkflowRuntime zum Hosten workflowbasierter WCF-Dienste an.|  
|[\<UseRequestHeadersForMetadataAddress >](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ServiceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|Eine Auflistung von Dienstverhaltenselementen.|
