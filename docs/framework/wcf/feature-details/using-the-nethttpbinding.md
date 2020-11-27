---
title: Verwenden der NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 85a81c353e779800a9aa371658f2f799365b759d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282027"
---
# <a name="using-the-nethttpbinding"></a>Verwenden der NetHttpBinding

<xref:System.ServiceModel.NetHttpBinding> ist eine für die Nutzung von HTTP- oder WebSocket-Diensten entwickelte Bindung, die standardmäßig die binäre Codierung verwendet. <xref:System.ServiceModel.NetHttpBinding> erkennt, ob sie mit einem Anforderung-Antwort-Vertrag oder einem Duplexvertrag verwendet wird, und ändert das Verhalten entsprechend, indem HTTP für Anforderung-Antwort-Verträge und WebSockets für Duplexverträge verwendet wird. Dieses Verhalten kann mit der <xref:System.ServiceModel.Channels.WebSocketTransportUsage>-Einstellung überschrieben werden:  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> : Erzwingt, dass websockets auch für Anforderung-Antwort-Verträge verwendet werden.  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> -Dadurch wird verhindert, dass websockets verwendet werden. Der Versuch, einen Duplexvertrag mit dieser Einstellung zu verwenden, löst eine Ausnahme aus.  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> : Dies ist der Standardwert und verhält sich wie oben beschrieben.  
  
 <xref:System.ServiceModel.NetHttpBinding> unterstützt zuverlässige Sitzungen im HTTP-Modus und WebSocket-Modus. Im WebSocket-Modus werden Sitzungen vom Transport bereitgestellt.  
  
> [!WARNING]
> Wenn  verwendet wird und TransferMode für die Bindung auf TransferMode.Streamed festgelegt ist, verursachen große Datenströme ein Deadlock und der Aufruf ein Timeout. Um dieses Problem zu umgehen, senden Sie kleinere Nachrichten oder verwenden TransferMode.Buffered.  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a>Konfigurieren eines Diensts für die Verwendung von "NetHttpBinding"  

 <xref:System.ServiceModel.NetHttpBinding> kann wie jede andere Bindung konfiguriert werden. Der folgende Konfigurationsausschnitt veranschaulicht, wie ein WCF-Dienst mit <xref:System.ServiceModel.NetHttpBinding> konfiguriert wird.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    ...
  </system.serviceModel>  
```  
  
 Der folgende Codeausschnitt veranschaulicht, wie <xref:System.ServiceModel.NetHttpBinding> im Code hinzugefügt wird.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);
        }  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren von Bindungen für Dienste](../configuring-bindings-for-wcf-services.md)
- [Bindungen](bindings.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
- [Duplexdienste](duplex-services.md)
