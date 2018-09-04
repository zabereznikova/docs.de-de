---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: e5f34dca83c8d3d08d27fb72bee5af2a89ac6b9f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511913"
---
# <a name="ltwebsocketsettingsgt"></a>&lt;webSocketSettings&gt;
Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.  
  
\<system.ServiceModel>  
\<bindings>  
\<netHttpBinding>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|createNotificationOnConnection|Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.|  
|disablePayloadMasking|Gibt an, ob die WebSocket-Maske deaktiviert ist.|  
|keepAliveInterval|Gibt das Keep-Alive-Intervall an.|  
|maxPendingConnections|Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.|  
|receiveBufferSize|Gibt die Größe des Empfangspuffers an.|  
|sendBufferSize|Gibt die Größe des Sendepuffers an.|  
|subProtocol|Gibt das WebSocket-Unterprotokoll an.|  
|transportUsage|Gibt an, wann WebSockets verwendet wird.|  
  
## <a name="transportusage-attribute"></a>transportUsage-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|WhenDuplex|Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.|  
|Always|Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.|  
|Nie|Verwendet niemals das WebSocket-Protokoll.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|\<netHttpBinding>|Gibt das NetHttpBinding-Element an.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der \<WebSocketSettings > Element.  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
