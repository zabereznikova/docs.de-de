---
title: '&lt;udpTransportSettings&gt; von &lt;udpAnnouncementEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
ms.openlocfilehash: 624dbada56a609452310218d26c5c6ff0ca49d64
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767075"
---
# <a name="ltudptransportsettingsgt-of-ltudpannouncementendpointgt"></a>&lt;udpTransportSettings&gt; von &lt;udpAnnouncementEndpoint&gt;
Dieses Konfigurationselement macht UDP-transporteinstellungen für [ \<UdpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md).  
  
\<system.ServiceModel>  
\<StandardEndpoints >  
\<UdpAnnouncementEndpoint >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <udpAnnouncementEndpoint>
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
    </udpAnnouncementEndpoint>
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
|maxMulticastRetransmitCount|Eine ganze Zahl, die die maximale Anzahl angibt, die eine Nachricht (zusätzlich zum ersten Senden) neu gesendet werden soll.<br /><br /> Der Standard ist 2.|  
|maxPendingMessageCount|Eine ganze Zahl, die die maximale Anzahl an Nachrichten angibt, die empfangen, jedoch noch nicht aus dem InputQueue-Element für eine einzelne Channelinstanz entfernt wurden.  Wenn das InputQueue-Element das Limit für die Anzahl ausstehender Nachrichten erreicht hat, wird die Nachricht verworfen.<br /><br /> Der Standard ist 32.|  
|maxReceivedMessageSize|Eine ganze Zahl, die die maximale Größe einer Nachricht angibt, die von der Bindung verarbeitet werden kann.<br /><br /> Der Standardwert ist 65507.|  
|maxUnicastRetransmitCount|Eine ganze Zahl, die die maximale Anzahl angibt, die eine Nachricht (zusätzlich zum ersten Senden) neu gesendet werden soll.  Wenn die Nachricht an eine Unicastadresse gesendet und eine Antwortnachricht mit einem entsprechenden RelatesTo-Header empfangen wird, dann wird die Neuübertragung möglicherweise frühzeitig beendet (bevor die Nachricht die konfigurierte Anzahl an Malen neu gesendet wurde).<br /><br /> Der Standardwert ist 1.|  
|multicastInterfaceId|Eine Zeichenfolge, die den Netzwerkadapter eindeutig identifiziert, der zum Senden und Empfangen von Multicastdatenverkehr auf Computern mit mehreren Adressen verwendet werden soll. Zur Laufzeit verwendet der Transport diesen Attributwert, um den Schnittstellenindex nachzuschlagen, der dann zum Festlegen der Socketoptionen `IP_MULTICAST_IF` und `IPV6_MULTICAST_IF` verwendet wird.  Beim Beitreten zu einer Multicastgruppe wird der gleiche Schnittstellenindex verwendet.<br /><br /> Der Standardwert ist `null`.|  
|socketReceiveBufferSize|Eine ganze Zahl, die die Empfangspuffergröße auf dem zugrunde liegenden WinSock-Socket angibt.<br /><br /> Ein Benutzer eines empfangenden Kanals kann dieses Attribut für die Bindung verwenden, um zu steuern, wie sich das System verhält, wenn es Daten empfängt.  Wenn zum Beispiel eine Anwendung vorliegt, die mit dem maximalen Schwellenwert eingehende WCF-Nachrichten verarbeitet, werden Nachrichten durch Verwendung eines höheren Werts für dieses Attribut im WinSock-Puffer gestapelt, während sie darauf warten, von der Anwendung verarbeitet zu werden.  Bei einem niedrigeren Wert würden in diesem Fall Nachrichten verworfen. Dieses Attribut macht die zugrunde liegende `SO_RCVBUF`-Socketoption verfügbar. Der Attributwert muss mindestens `maxReceivedMessageSize` sein.   Wenn Sie diesen Attributwert auf einen niedrigeren Wert festlegen als `maxReceivedMessageSize`, wird eine Laufzeitausnahme ausgelöst.<br /><br /> Der Standardwert ist 65536.|  
|timeToLive|Eine ganze Zahl, die die Anzahl an Netzwerksegmenthops angibt, die ein Multicastpaket durchlaufen kann.  Dieses Attribut macht die den Socketoptionen `IP_MULTICAST_TTL` und `IP_TTL` zugeordnete Funktionalität verfügbar.<br /><br /> Der Standardwert ist 1.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<UdpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|Ein Standardendpunkt mit festem Ankündigungsvertrag und fester UDP-Transportbindung.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Discovery.UdpTransportSettings>
