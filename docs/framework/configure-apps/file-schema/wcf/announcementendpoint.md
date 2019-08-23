---
title: <announcementEndpoint>
ms.date: 03/30/2017
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
ms.openlocfilehash: aa4cd8f4d7dcfa438ede71c394f1d0b0ac6faa50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926552"
---
# <a name="announcementendpoint"></a>\<announcementEndpoint>
Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ankündigungsvertrag. Die Verfügbarkeit eines Diensts kann optional angekündigt werden, indem beim Öffnen bzw. Schließen des Diensts eine Online- bzw. Offline-Ankündigungsnachricht gesendet wird. Ein Windows Communication Foundation (WCF)-Dienst gibt die Ankündigungs Endpunkte im [ \<servicediscovery->](servicediscovery.md) Element an und verwendet den "-Dienst", um die Ankündigungen auszuführen. Ein Client, der auf die Ankündigung von einem anderen Dienst lauschen möchte, fungiert tatsächlich als WCF-Dienst. Daher müssen Sie die Ankündigungs Endpunkte für diesen Client im [ \<Abschnitt Dienste >](services.md) konfigurieren.  
  
\<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxAnnouncementDelay="Timespan"
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|discoveryVersion|Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt. Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005. Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion>.|  
|maxAnnouncementDelay|Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis eine Hello-Nachricht gesendet wird. Die Wartezeit für diese Nachrichten ist ein zufälliger Zeitwert zwischen 0 und dem Wert dieses Attributs. Dieses Attribut wird zur Angabe einer kurzen, zufällig festgelegten Verzögerung verwendet, um Netzwerküberlastungen zu verhindern, wenn ein Netzwerk ausfällt und alle Dienste zur gleichen Zeit wieder in den Onlinestatus wechseln.|  
|Name|Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt. Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Client, der über http und peernet eine Überwachung auf Ankündigungsnachrichten durchführt.  
  
```xml  
<services>
  <service name="ServiceAnnouncementListener">
    <endpoint name="httpAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="basicHttpBinding"
              address="announcements" />
    <endpoint name="peerNetAnnouncementEndpoint"
              kind="announcementEndpoint"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  ...
  </service>
</services>

<standardEndpoints>
  <announcementEndpoint>
    <standardEndpoint name="httpAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
    <standardEndpoint name="peerNetAnnouncementEndpoint"
                      version="WSDiscoveryApril2005" />
  </announcementEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
