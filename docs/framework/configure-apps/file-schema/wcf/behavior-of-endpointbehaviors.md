---
title: <behavior> von <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: f14e80798a9b088508f23d718c8b386286ad65a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919842"
---
# <a name="behavior-of-endpointbehaviors"></a>\<Verhaltens > von \<endpointBehavior >
Das `behavior`-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Endpunkts. Jedes Verhalten wird durch seinen `name` indiziert. Endpunkte können über diesen Namen mit den Verhalten verknüpft sein. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält. Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.|  
|[\<callbackDebug>](callbackdebug.md)|Gibt das Dienst Debuggen für ein Windows Communication Foundation (WCF)-Rückruf Objekt an.|  
|[\<callbackTimeouts>](callbacktimeouts.md)|Gibt das Timeout für den Clientrückruf an.|  
|[\<clientVia>](clientvia.md)|Gibt die Route an, die eine Nachricht nehmen sollte.|  
|[\<dataContractSerializer>](datacontractserializer.md)|Speichert die Konfigurationsinformationen für DataContractSerializer.|  
|[\<dispatchersynchronisierungs->](dispatchersynchronization.md)|Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.|  
|[\<enableWebScript>](enablewebscript.md)|Aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann. Das Verhalten sollte nur in Verbindung mit der \<WebHttpBinding-> Standard Bindung oder dem \<> Bindungs Element webMessageEncoding verwendet werden.|  
|[\<endpointDiscovery>](endpointdiscovery.md)|Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.|  
|[\<soapProcessing>](soapprocessing.md)|Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.|  
|[\<synchronousreceive->](synchronousreceive-element.md)|Gibt das Laufzeitverhalten für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung an. Es enthält keine Attribute oder untergeordnete Elemente.|  
|[\<transactedBatching>](transactedbatching.md)|Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.|  
|[\<webHttp>](webhttp.md)|Gibt WebHttpBehavior anhand der Konfiguration in einem Endpunkt an. Wenn dieses Verhalten in Verbindung mit der \<WebHttpBinding-> Standard Bindung verwendet wird, wird das webprogrammier Modell für einen WCF-Dienst aktiviert.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Eine Auflistung von Endpunktverhaltenselementen.|
