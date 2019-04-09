---
title: <udpTransportSettings>
ms.date: 03/30/2017
ms.assetid: 842d92e9-6199-4ec5-b2d1-58533054e1f0
ms.openlocfilehash: f5be9681dc69fd68dfdfa90f4eb305dc4aa4514b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218497"
---
# <a name="udptransportsettings"></a>\<udpTransportSettings>
Dieses Konfigurationselement macht UDP-transporteinstellungen für [ \<UdpDiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md).  
  
\<system.ServiceModel>  
\<standardEndpoints>  
\<udpDiscoveryEndpoint>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer"
                              maxBufferPoolSize="Integer"
                              maxMulticastRetransmitCount="Integer"
                              maxPendingMessageCount="Integer"
                              maxReceivedMessageSize="Integer"
                              maxUnicastRetransmitCount="Integer"
                              multicastInterfaceId="String"
                              socketReceiveBufferSize="Integer"
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|duplicateMessageHistoryLength|Eine ganze Zahl, die die maximale Anzahl an Nachrichtenhashes angibt, die vom Transport zum Identifizieren von doppelten Nachrichten verwendet werden.  Die Erkennung doppelter Nachrichten wird auf TransportManager-Ebene ausgeführt. Mit dem Wert 0 wird die Erkennung doppelter Nachrichten deaktiviert.<br /><br /> Dieses Attribut ermöglicht Systemadministratoren und Entwicklern, Algorithmen zur Erkennung doppelter Nachrichten zu deaktivieren. Dies kann nützlich sein, wenn Sie einen eigenen Algorithmus zur Erkennung doppelter Nachrichten implementieren möchten.<br /><br /> Der Standard ist 4112.|  
|maxBufferPoolSize|Eine ganze Zahl, die die maximale Größe von Pufferpools angibt, die vom Transport verwendet werden.|  
|maxMulticastRetransmitCount|Eine ganze Zahl, die die maximale Anzahl angibt, die eine Nachricht (zusätzlich zum ersten Senden) neu gesendet werden soll.<br /><br /> Der Standardwert ist&amp;#160;2.|  
|maxPendingMessageCount|Eine ganze Zahl, die die maximale Anzahl an Nachrichten angibt, die empfangen, jedoch noch nicht aus dem InputQueue-Element für eine einzelne Channelinstanz entfernt wurden.  Wenn das InputQueue-Element das Limit für die Anzahl ausstehender Nachrichten erreicht hat, wird die Nachricht verworfen.<br /><br /> Der Standard ist 32.|  
|maxReceivedMessageSize|Eine ganze Zahl, die die maximale Größe einer Nachricht angibt, die von der Bindung verarbeitet werden kann.<br /><br /> Der Standardwert ist 65507.|  
|maxUnicastRetransmitCount|Eine ganze Zahl, die die maximale Anzahl angibt, die eine Nachricht (zusätzlich zum ersten Senden) neu gesendet werden soll.  Wenn die Nachricht an eine Unicastadresse gesendet und eine Antwortnachricht mit einem entsprechenden RelatesTo-Header empfangen wird, dann wird die Neuübertragung möglicherweise frühzeitig beendet (bevor die Nachricht die konfigurierte Anzahl an Malen neu gesendet wurde).<br /><br /> Der Standardwert ist 1.|  
|multicastInterfaceId|Eine Zeichenfolge, die den Netzwerkadapter eindeutig identifiziert, der zum Senden und Empfangen von Multicastdatenverkehr auf Computern mit mehreren Adressen verwendet werden soll. Zur Laufzeit verwendet der Transport diesen Attributwert, um den Schnittstellenindex nachzuschlagen, der dann zum Festlegen der Socketoptionen `IP_MULTICAST_IF` und `IPV6_MULTICAST_IF` verwendet wird.  Beim Beitreten zu einer Multicastgruppe wird der gleiche Schnittstellenindex verwendet.<br /><br /> Der Standardwert ist `null`.|  
|socketReceiveBufferSize|Eine ganze Zahl, die die Empfangspuffergröße auf dem zugrunde liegenden WinSock-Socket angibt.<br /><br /> Ein Benutzer eines empfangenden Kanals kann dieses Attribut für die Bindung verwenden, um zu steuern, wie sich das System verhält, wenn es Daten empfängt.  Wenn zum Beispiel eine Anwendung vorliegt, die mit dem maximalen Schwellenwert eingehende WCF-Nachrichten verarbeitet, werden Nachrichten durch Verwendung eines höheren Werts für dieses Attribut im WinSock-Puffer gestapelt, während sie darauf warten, von der Anwendung verarbeitet zu werden.  Bei der Verwendung eines niedrigeren Werts in derselben Situation werden Meldungen verworfen. Dieses Attribut macht die zugrunde liegende `SO_RCVBUF` Socketoption. Dieser Attributwert muss mindestens die Größe des `maxReceivedMessageSize`.   Festlegen auf einen Wert kleiner als die `maxReceivedMessageSize` führt zu einer Laufzeitausnahme.<br /><br /> Der Standardwert ist 65536.|  
|timeToLive|Eine ganze Zahl, die die Anzahl an Netzwerksegmenthops angibt, die ein Multicastpaket durchlaufen kann.  Dieses Attribut macht die den Socketoptionen `IP_MULTICAST_TTL` und `IP_TTL` zugeordnete Funktionalität verfügbar.<br /><br /> Der Standardwert ist 1.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<udpDiscoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|Ein Standardendpunkt mit festem Ermittlungsvertrag und fester UDP-Transportbindung.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>
