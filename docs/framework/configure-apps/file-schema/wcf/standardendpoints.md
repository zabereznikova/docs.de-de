---
title: "&lt;standardEndpoints&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;standardEndpoints&gt;
Dieser Konfigurationsabschnitt ermöglicht die Definition einer Auflistung von Standardendpunkten, bei denen es sich um wiederverwendbare vorkonfigurierte Endpunkte handelt.  Bei einem Standardendpunkt werden eines oder mehrere der Attribute für Adresse, Bindung und Vertrag vorab festgelegt.  Zum Beispiel ist der Vertrag im Ermittlungsendpunkt ein fester Wert.  Sie können Standardendpunkte auch verwenden, um Dienstendpunkte mit neuen Eigenschaften zu erweitern, ähnlich wie bei der Definition benutzerdefinierter Bindungen.  
  
 \<system.ServiceModel\>  
  
## Syntax  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
  
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag.  Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online\- bzw. Offline\-Ankündigungsnachricht gesendet wird.  Ein [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Dienst gibt die Ankündigungsendpunkte im [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)\-Element an und führt die Ankündigungen über das AnnouncementClient\-Element aus.  Ein Client, der eine Überwachung auf Ankündigungen von anderen Diensten durchführt, agiert als [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienst. Aus diesem Grund müssen Sie die Ankündigungsendpunkte für diesen Client im Abschnitt [\<Dienste\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) konfigurieren.|  
|[\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Definiert einen Standardendpunkt mit einem festen Ermittlungsvertrag.  Wenn es der Dienstkonfiguration hinzugefügt wird, gibt es an, wo die Überwachung auf Ermittlungsnachrichten erfolgen soll.  Wenn es der Clientkonfiguration hinzugefügt wird, gibt es an, wohin die Ermittlungsabfragen gesendet werden sollen.|  
|[\<dynamicEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/dynamicendpoint.md)|Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.|  
|[\<mexEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/mexendpoint.md)|Definiert einen Standardendpunkt mit einem festen IMetadataExchange\-Vertrag.  Da alle Metadatenaustausch\-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.|  
|[\<udpAnnoucementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|Definiert einen Standardendpunkt, der von Diensten verwendet wird, um Ankündigungsnachrichten über eine UDP\-Bindung zu senden.  Es weist einen festen Vertrag auf und unterstützt zwei Suchversionen.  Außerdem weist er eine feste UDP\-Bindung und einen Standardadresswert gemäß WS\-Discovery\-Spezifikationen \(WS\-Discovery Version April 2005 oder Version 1.1\) auf.  Sie können die Multicastadresse angeben, die zum Senden und Empfangen der Ankündigungsnachrichten verwendet werden soll.|  
|[\<udpDiscoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|Definiert einen Standardendpunkt, der für Suchvorgänge über eine UDP\-Multicastbindung vorkonfiguriert ist.  Dieser Endpunkt hat einen festen Vertrag und unterstützt zwei WS\-Discovery\-Protokollversionen.  Außerdem weist er eine feste UDP\-Bindung und eine Standardadresse gemäß WS\-Discovery\-Spezifikationen \(WS\-Discovery Version April 2005 oder Version 1.1\) auf.|  
|[\<webHttpEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpendpoint.md)|Definiert einen Standardendpunkt mit einer festen [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)\-Bindung, die das [\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)\-Verhalten automatisch hinzufügt.  Verwenden Sie diesen Endpunkt, wenn Sie einen REST\-Dienst schreiben.|  
|[\<webScriptEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webscriptendpoint.md)|Definiert einen Standardendpunkt mit einer festen [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)\-Bindung, die das [\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)\-Verhalten automatisch hinzufügt.  Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX\-Anwendung aufgerufen wird.|  
|[\<workflowControlEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowcontrolendpoint.md)|Definiert einen Standardendpunkt zur Steuerung der Ausführung von Workflowinstanzen \(create, run, suspend, terminate usw.\).|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|\<system.ServiceModel\>|Das Stammelement aller WCF\-Konfigurationselemente.|  
  
## Siehe auch  
 [Standardendpunkte](../../../../../docs/framework/wcf/feature-details/standard-endpoints.md)