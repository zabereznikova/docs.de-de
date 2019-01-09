---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: bf9229411143345847247f36de07b5c014d3f259
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149599"
---
# <a name="ltnamedpipetransportgt"></a>&lt;namedPipeTransport&gt;
Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.  
  
\<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<NamePipeTransport >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|ChannelInitializationTimeout|Ruft ab oder legt einen <xref:System.TimeSpan> , bestimmt die maximale Zeit, die ein Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird.|  
|ConnectionBufferSize|Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.|  
|hostNameComparisonMode|Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.|  
|manualAddressing|Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.|  
|maxBufferPoolSize|Übernimmt oder bestimmt die maximale Größe in Byte von Pufferpools, die vom Transport verwendet werden.|  
|maxBufferSize|Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest. Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.|  
|MaxOutputDelay|Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.|  
|maxPendingAccepts|Übernimmt oder bestimmt die maximale Anzahl von Kanälen, die einen Dienst auf einen Listener anbieten kann für die Verarbeitung von eingehenden Verbindungen mit dem Dienst warten.|  
|maxPendingConnections|Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.|  
|maxReceivedMessageSize|Ermittelt und definiert die maximale zulässige Nachrichtengröße in Bytes, die empfangen werden können.|  
|transferMode|Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.|  
|[\<ConnectionPoolSettings > von \<NamedPipeTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
Dieser Transport verwendet URIs im Format "net.pipe://hostname/path". Andere URI-Komponenten sind optional.  
  
Das `namedPipeTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes-Transportprotokoll implementiert. Dieser Transport wird für Windows Communication Foundation (WCF)-zu-WCF-Kommunikation auf dem Computer verwendet.  
  
## <a name="see-also"></a>Siehe auch  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
[Transporte](../../../../../docs/framework/wcf/feature-details/transports.md)   
[Auswählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
[Bindungen](../../../../../docs/framework/wcf/bindings.md)   
[Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
[Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
[\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
