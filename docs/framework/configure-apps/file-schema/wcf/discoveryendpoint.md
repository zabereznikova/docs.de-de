---
title: <discoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 32b14f8fb3235040a51455f2099a403c8312c699
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855394"
---
# \<discoveryEndpoint>

Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen Ermittlungsvertrag. Wenn es der Dienstkonfiguration hinzugefügt wird, gibt es an, wo die Überwachung auf Ermittlungsnachrichten erfolgen soll. Wenn es der Clientkonfiguration hinzugefügt wird, gibt es an, wohin die Ermittlungsabfragen gesendet werden sollen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryEndpoint>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute

| attribute        | BESCHREIBUNG |  
| ---------------- | ----------- |  
| discoveryMode    | Eine Zeichenfolge, die den Modus des Suchprotokolls angibt. Gültige Werte sind "Adhoc" und "Managed". Im verwalteten Modus benötigt das Protokoll einen Suchproxy, der als Repository sichtbarer Dienste fungiert. Der Ad-hoc-Modus erfordert, dass das Protokoll den UDP-Multicastmechanismus verwendet, um verfügbare Dienste zu suchen. Weitere Informationen zur-Eigenschaft finden Sie unter <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A> . |  
| discoveryVersion | Eine Zeichenfolge, die eine der zwei Versionen des WS-Suchprotokolls angibt. Gültige Werte sind WSDiscovery11 und WSDiscoveryApril2005. Dieser Wert ist vom Typ <xref:System.ServiceModel.Discovery.DiscoveryVersion>. |  
| maxResponseDelay | Ein Timespan-Wert, der den maximalen Wert für die Verzögerung angibt, den das Suchprotokoll wartet, bis bestimmte Meldungen gesendet werden, z. B. "Probe Match" oder "Resolve Match".<br /><br /> Wenn alle ProbeMatches zur gleichen Zeit gesendet werden, kann es zu einer Netzwerküberlastung kommen. Um zu verhindern, dass dieser Fall eintritt, werden ProbeMatches mit einer zufälligen Verzögerung zwischen den ProbeMatches gesendet. Die zufällige Verzögerung liegt im Bereich zwischen 0 und dem Wert, der von diesem Attribut festgelegt wurde. Wenn dieses Attribut auf 0 festgelegt wird, werden die ProbeMatches-Meldungen in einer engen Schleife ohne Verzögerung gesendet. Andernfalls werden die ProbeMatches-Meldungen mit einer zufällig festgelegten Verzögerung gesendet, sodass die Gesamtzeit zum Senden aller ProbeMatches-Meldungen den maxResponseDelay-Wert nicht überschreitet. Dieser Wert ist nur für Dienste relevant, er wird nicht von Clients verwendet. |  
| `name`           | Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt. Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet. |  
  
### <a name="child-elements"></a>Untergeordnete Elemente

Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente

| Element | Beschreibung |  
| ------- | ----------- |  
| [\<standardEndpoints>](standardendpoints.md) | Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind. |  
  
## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt einen Dienst, der einen Multicasttransport in einem Peernetzwerk auf Ermittlungsnachrichten überwacht. Im Beispiel wird explizit die Version WS-Discovery April 2005 angegeben.  
  
Die Standardendpunktkonfiguration wird pro Dienst definiert und kann nicht dienstübergreifend freigegeben werden. Wenn ein anderer Dienst den gleichen Ermittlungsendpunkt haben soll, muss dem Abschnitt dieses Diensts die gleiche Konfiguration hinzugefügt werden.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="peerNetDiscovery"
              binding="peerTcpBinding"
              address="net.p2p://discoveryMesh/multicast"
              kind="discoveryEndpoint"
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"
              bindingConfiguration="discoveryPeerTcpBindingConfig" />
  </service>
</services>
<standardEndpoints>
  <discoveryEndpoint>
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"
                      version="WSDiscoveryApril2005" />
  </discoveryEndpoint>
</standardEndpoints>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
