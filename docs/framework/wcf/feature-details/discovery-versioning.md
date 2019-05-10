---
title: Versionskontrolle für die Suche
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 3f90fc5183e974b9045c156e0ae74099abfbc41a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626955"
---
# <a name="discovery-versioning"></a>Versionskontrolle für die Suche
Dieses Thema enthält eine kurze Übersicht über die Implementierung einiger neuer Suchfunktionen. Es enthält außerdem eine Übersicht über die Auswahl der zu verwendenden Suchversion.  
  
## <a name="discovery-versioning"></a>Versionskontrolle für die Suche  
 Die Suchfunktion verfügt über die Unterstützung für drei Versionen des WS_Discovery-Protokolls. Mithilfe der Such-APIs können Sie auswählen, welche Version des Protokolls Sie verwenden möchten. In diesem Dokument werden die Einstellungen zur Versionskontrolle kurz beschrieben.  
  
 Die folgenden Discovery-Klassen verfügen jetzt über eine <xref:System.ServiceModel.Discovery.DiscoveryVersion>-Eigenschaft und verwenden in ihren Konstruktoren ein <xref:System.ServiceModel.Discovery.DiscoveryVersion>-Argument:  
  
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
### <a name="discoveryversionwsdiscoveryapril2005"></a>DiscoveryVersion.WSDiscoveryApril2005  
 Bereitstellen von <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> als Konstruktor Parameter die Implementierung die Version "april2005" des WS-Discovery-Protokolls verwendet wird. Diese Version entspricht der veröffentlichten Version der WS-Discovery-Protokollspezifikation. Sie sollten diese Version bei Interaktionen mit älteren Anwendungen verwenden, die die Version "April2005" der WS-Suche nutzen.  
  
### <a name="discoveryversionwsdiscovery11"></a>DiscoveryVersion.WSDiscovery11  
 Die von den APIs verwendeten standardermittlungsversion ist <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>. Dies ist die momentane Standardversion des WS-Discovery-Protokolls.  
  
## <a name="discoveryversionwsdiscoverycd1"></a>DiscoveryVersion.WSDiscoveryCD1  
 Das Bereitstellen von <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> als Konstruktorparameter führt dazu, dass die Implementierung die Version "Committee Draft 1" des WS-Discovery-Protokolls verwendet. Sie sollten diese Version des Protokolls bei Interaktionen mit Implementierungen verwenden, die die CD1-Version des WS-Discovery-Protokolls nutzen.  
  
## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a>Unterstützen von mehreren UDP-Suchendpunkten für verschiedene Suchversionen auf einem einzelnen Diensthost  
 Es kann erforderlich sein, auf einem einzelnen Diensthost mehrere UDP-Suchendpunkte für verschiedene Suchversionen verfügbar zu machen. Dazu müssen Sie eine eindeutige Adresse für jeden UDP-Suchendpunkt angeben. Das folgende Beispiel zeigt die dazu erforderliche Vorgehensweise.  
  
```  
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);  
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
  
newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");  
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionAril2005");  
  
serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);  
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);  
```
