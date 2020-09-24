---
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 6d4302e1840f58e2daad855942493cc96b7d5e34
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158668"
---
# \<tcpTransport>

Definiert einen TCP-Transport, der von einem Kanal zum Übertragen von Nachrichten für eine benutzerdefinierte Bindung verwendet werden kann.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tcpTransport>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|channelInitializationTimeout|Ruft das Zeitlimit zum Initialisieren eines Kanals ab, der akzeptiert werden soll, oder legt das Limit fest.  Die maximale Zeit in Sekunden, in der sich der Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird. Dieses Kontingent umfasst die Zeit, die eine TCP-Verbindung zum Authentifizieren mit dem .net-Nachrichtenrahmen Protokoll benötigt. Ein Client muss vorab einige Daten senden, bevor der Server über genügend Informationen zum Ausführen der Authentifizierung verfügt. Der Standardwert ist 30 Sekunden.|  
|connectionbuffersize|Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.|  
|HostNameComparisonMode|Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.|  
|listenBacklog|Die maximale Anzahl der Verbindungsanforderungen in der Warteschlange, die für einen Webdienst ausstehen können. Das `connectionLeaseTimeout`-Attribut beschränkt die Zeit, die ein Client wartet, bevor eine Verbindungsausnahme ausgelöst wird. Dies ist eine Eigenschaft auf Socketebene, die die maximale Anzahl der in der Warteschlange eingereihten Verbindungsanforderungen steuert, die für einen Webdienst ausstehend sein können. Wenn der listenrückstand zu niedrig ist, werden Anforderungen von WCF nicht mehr akzeptiert. Daher werden neue Verbindungen gelöscht, bis der Server einige der vorhandenen Verbindungen in der Warteschlange bestätigt. Der Standardwert ist 16 * Anzahl von Prozessoren.|  
|manualAddressing|Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.|  
|maxBufferPoolSize|Ruft die maximale Größe von Pufferpools ab, die vom Transport verwendet werden, oder legt diese fest.|  
|maxBufferSize|Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest. Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.|  
|maxoutputdelay|Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.|  
|maxPendingAccepts|Ruft die maximale Anzahl ausstehender asynchroner Annahmevorgänge ab, die für die Verarbeitung beim Dienst eingehender Verbindungen zur Verfügung stehen, oder legt die maximale Anzahl fest.|  
|maxPendingConnections|Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.|  
|maxReceivedMessageSize|Ruft die maximal zulässige Größe der Nachrichten ab, die empfangen werden können, und legt diese fest.|  
|portSharingEnabled|Ein boolescher Wert, der angibt, ob die TCP-Anschlussfreigabe für diese Verbindung aktiviert ist. Wenn dies `false` ist, verwendet jede Bindung ihren eigenen Anschluss. Der Standardwert lautet `false`.<br /><br /> Diese Einstellung ist nur für Dienste relevant. Auf Clients hat dies keine Auswirkung.<br /><br /> Bei Verwendung dieser Einstellung muss der Windows Communication Foundation (WCF)-TCP-Anschlussfreigabedienst aktiviert werden, indem der Starttyp auf Manuell oder Automatisch gesetzt wird.|  
|teredoEnabled|Ein boolescher Wert, der angibt, ob das Teredo-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird. Der Standardwert lautet `false`.<br /><br /> Mit dieser Eigenschaft wird das Teredo-Protokoll für das zugrunde liegende TCP-Socket aktiviert. Weitere Informationen finden Sie unter [Übersicht über Teredo](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).<br /><br /> Diese Eigenschaft gilt nur für Windows XP SP2 und Windows Server 2003. Windows Vista verfügt über eine Computer weite Konfigurationsoption für Teredo. Wenn Sie also Vista ausführen, wird diese Eigenschaft ignoriert. Um das Teredo-Protokoll verwenden zu können, müssen der Client und die Dienstcomputer über den IPv6-Stapel von Microsoft verfügen und ordnungsgemäß konfiguriert sein.|  
|transferMode|Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.|  
|connectionPoolSettings|Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Bemerkungen  

 Dieser Transport verwendet URIs im Format "net.tcp://hostname:port/path". Andere URI-Komponenten sind optional.  
  
 Das `tcpTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das TCP-Transportprotokoll implementiert. Dieser Transport ist für die Kommunikation zwischen WCF und WCF optimiert.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportprotokolle](../../../wcf/feature-details/transports.md)
- [Wählen eines Transports](../../../wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
