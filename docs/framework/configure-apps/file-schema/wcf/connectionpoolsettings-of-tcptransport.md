---
title: <connectionPoolSettings> von <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398097"
---
# <a name="connectionpoolsettings-of-tcptransport"></a>\<connectionPoolSettings> von \<tcpTransport>
Gibt zusätzliche Verbindungspooleinstellungen für einen TCP-Transport an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`groupName`|Eine Zeichenfolge, die den Namen des Verbindungspools für ausgehende Kanäle definiert. Im Streammodus werden keine Verbindungen freigegeben, was bedeutet, dass Verbindungspooling deaktiviert wird. Der Standardwert ist eine "standardmäßige" Zeichenfolge. Sie können diesen Wert ändern, um die Verbindungen für einen bestimmten Client in separate Gruppen zu isolieren.|  
|`idleTimeout`|Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, in der sich die Verbindung im Leerlauf befinden kann, bevor sie unterbrochen wird. Der Standardwert ist 00:02:00.|  
|`leaseTimeout`|Eine <xref:System.TimeSpan>, die angibt, wann eine aktive Verbindung geschlossen wird. Der Standardwert ist 00:05:00.<br /><br /> Eine Verbindung wird geschlossen, nachdem sie an den Verbindungscache zurückgegeben wurde, und nicht während einer aktiven Übertragung. Der vom TCP-Transport verwendete Verbindungscache erstellt die für jeden Endpunkt erforderlichen neuen Verbindungen bis hin zu einem Cachelimit, das von `maxOutboundConnectionsPerEndpoint.` festgelegt wird.|  
|`maxOutboundConnectionsPerEndpoint`|Eine positive ganze Zahl, die die maximale Anzahl von Verbindungen zu einem Remoteendpunkt angibt, die vom Dienst initiiert werden. Verbindungen oberhalb des Limits werden in eine Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird. `idleTimeout` schränkt die Dauer ein, in der Verbindungen in der Warteschlange bleiben können, bevor eine Ausnahme ausgelöst wird. Der Standardwert ist 10.<br /><br /> Dieses Attribut beschränkt die Anzahl gleichzeitiger aktiver Verbindungen vom Client zu einem bestimmten Dienstendpunkt. Wenn dieser Wert durch zusätzliche aktive Clientverbindungen überstiegen wird, antwortet der Dienst dem Client möglicherweise nicht. In diesem Fall sollte dieser Wert angepasst werden, um die maximale Anzahl der erwarteten gleichzeitigen Clientverbindungen in einem bestimmten Endpunkt zu übertreffen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|Definiert einen Transport, der bewirkt, dass ein Kanal Nachrichten mithilfe von benannten Pipes überträgt.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportprotokolle](../../../wcf/feature-details/transports.md)
- [Wählen eines Transports](../../../wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../wcf/bindings.md)
- [Erweitern von Bindungen](../../../wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
