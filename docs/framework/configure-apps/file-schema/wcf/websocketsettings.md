---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 94a5883c37221a8d637a188fe42aad220a332575
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582397"
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
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
