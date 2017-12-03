---
title: '&lt;standardEndpoints&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e0e13dd8a5ac35f47e258d2a49d65c32e8c91f1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltstandardendpointsgt"></a>&lt;standardEndpoints&gt;
Dieser Konfigurationsabschnitt ermöglicht die Definition einer Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt. Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt. Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert. Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.  
  
 \<System. ServiceModel >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<AnnouncementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag. Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird. Ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Dienst gibt an, die ankündigungsendpunkte in der [ \<ServiceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) Element- und verwendet die AnnouncementClient die Ankündigungen ausführen. Ein Client möchte, überwacht die Ankündigung aus anderen Dienst tatsächlich als dient eine [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] Dienst; daher müssen Sie konfigurieren, die ankündigungsendpunkte für den Client in der [ \<Services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) Abschnitt.|  
|[\<DiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Definiert einen Standardendpunkt mit einem festen Ermittlungsvertrag. Wenn es der Dienstkonfiguration hinzugefügt wird, gibt es an, wo die Überwachung auf Ermittlungsnachrichten erfolgen soll. Wenn es der Clientkonfiguration hinzugefügt wird, gibt es an, wohin die Ermittlungsabfragen gesendet werden sollen.|  
|[\<DynamicEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/dynamicendpoint.md)|Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.|  
|[\<MexEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/mexendpoint.md)|Definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag. Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.|  
|[\<UdpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|Definiert einen Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsnachrichten über eine UDP-Bindung zu senden. Es weist einen festen Vertrag auf und unterstützt zwei Suchversionen. Außerdem weist er eine feste UDP-Bindung und einen Standardadresswert gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf. Sie können die Multicastadresse angeben, die zum Senden und Empfangen der Ankündigungsnachrichten verwendet werden soll.|  
|[\<UdpDiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|Definiert einen Standardendpunkt, der für Suchvorgänge über eine UDP-Multicastbindung vorkonfiguriert ist. Dieser Endpunkt hat einen festen Vertrag und unterstützt zwei WS-Discovery-Protokollversionen. Außerdem weist er eine feste UDP-Bindung und eine Standardadresse gemäß WS-Discovery-Spezifikationen (WS-Discovery Version April 2005 oder Version 1.1) auf.|  
|[\<WebHttpEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpendpoint.md)|Definiert einen Standardendpunkt mit einer festen [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fügt automatisch Bindung, die [ \<WebHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) Verhalten. Verwenden Sie diesen Endpunkt, wenn Sie einen REST-Dienst schreiben.|  
|[\<WebScriptEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/webscriptendpoint.md)|Definiert einen Standardendpunkt mit einer festen [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fügt automatisch Bindung, die [ \<EnableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Verhalten. Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX-Anwendung aufgerufen wird.|  
|[\<WorkflowControlEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowcontrolendpoint.md)|Definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen (create, run, suspend, terminate usw.).|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|\<System. ServiceModel >|Das Stammelement aller WCF-Konfigurationselemente.|  
  
## <a name="see-also"></a>Siehe auch  
 [Standardendpunkte](../../../../../docs/framework/wcf/feature-details/standard-endpoints.md)
