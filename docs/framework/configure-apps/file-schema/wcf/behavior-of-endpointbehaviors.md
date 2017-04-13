---
title: "&lt;behavior&gt; von &lt;endpointBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# &lt;behavior&gt; von &lt;endpointBehaviors&gt;
Das `behavior`\-Element enthält eine Auflistung der Einstellungen für das Verhalten eines Endpunkts.  Jedes Verhalten wird durch seinen `name` indiziert.  Endpunkte können über diesen Namen mit den Verhalten verknüpft sein.  Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.  Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhalten finden Sie unter [Vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## Syntax  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <endpointBehaviors>  
       <behavior name="String" />  
    </endpointBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Name|Eine eindeutige Zeichenfolge, die den Konfigurationsnamen des Verhaltens enthält.  Dieser Wert muss eine benutzerdefinierte und eindeutige Zeichenfolge sein, da sie als identifizierende Zeichenfolge für das Element fungiert.  Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen.  Weitere Informationen zu Standardkonfiguration und zu namenlosen Bindungen und Verhalten finden Sie unter [Vereinfachte Konfiguration](../../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.|  
|[\<callbackDebug\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|Legt Dienstdebugging für ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Rückrufobjekt fest.|  
|[\<callbackTimeouts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|Gibt das Timeout für den Clientrückruf an.|  
|[\<clientVia\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|Gibt die Route an, die eine Nachricht nehmen sollte.|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|Speichert die Konfigurationsinformationen für DataContractSerializer.|  
|[\<dispatcherSynchronization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|Gibt ein Endpunktverhalten an, das einem Dienst das asynchrone Senden von Antworten ermöglicht.|  
|[\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|Aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX\-Webseiten genutzt werden kann.  Das Verhalten sollte nur in Verbindung mit der \<webHttpBinding\>\-Standardbindung oder dem \<webMessageEncoding\>\-Bindungselement verwendet werden.|  
|[\<endpointDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.|  
|[\<soapProcessing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|Definiert das Clientendpunktverhalten, das verwendet wird, um Nachrichten zwischen unterschiedlichen Bindungstypen und Nachrichtenversionen zu marshallen.|  
|[\<synchronousReceive\>](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|Gibt das Laufzeitverhalten für das Empfangen von Nachrichten in einem Dienst oder einer Clientanwendung an.  Es enthält keine Attribute oder untergeordnete Elemente.|  
|[\<transactedBatching\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.|  
|[\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|Gibt WebHttpBehavior anhand der Konfiguration in einem Endpunkt an.  Wenn dieses Verhalten zusammen mit der \<webHttpBinding\>\-Standardbindung verwendet wird, wird das Webprogrammiermodell für einen [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienst aktiviert.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<endpointBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Eine Auflistung von Endpunktverhaltenselementen.|