---
title: Verwenden der NetHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 56528078895ea7c624afaf716e9a26eabe335d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-nethttpbinding"></a>Verwenden der NetHttpBinding
<xref:System.ServiceModel.NetHttpBinding> ist eine für die Nutzung von HTTP- oder WebSocket-Diensten entwickelte Bindung, die standardmäßig die binäre Codierung verwendet. <xref:System.ServiceModel.NetHttpBinding> erkennt, ob sie mit einem Anforderung-Antwort-Vertrag oder einem Duplexvertrag verwendet wird, und ändert das Verhalten entsprechend, indem HTTP für Anforderung-Antwort-Verträge und WebSockets für Duplexverträge verwendet wird. Dieses Verhalten kann überschrieben werden, mithilfe der <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` Einstellung:  
  
1.  Always: Erzwingt die Verwendung von WebSockets sogar für Anforderung-Antwort-Verträge.  
  
2.  Never: Verhindert die Verwendung von WebSockets. Der Versuch, einen Duplexvertrag mit dieser Einstellung zu verwenden, löst eine Ausnahme aus.  
  
3.  WhenDuplex: Dies ist der Standardwert, der das oben beschriebene Verhalten aufweist.  
  
 <xref:System.ServiceModel.NetHttpBinding> unterstützt zuverlässige Sitzungen im HTTP-Modus und WebSocket-Modus. Im WebSocket-Modus werden Sitzungen vom Transport bereitgestellt.  
  
> [!WARNING]
>  Wenn <xref:System.ServiceModel.NetHttpBinding> verwendet wird und TransferMode für die Bindung auf TransferMode.Streamed festgelegt ist, verursachen große Datenströme ein Deadlock und der Aufruf ein Timeout. Um dieses Problem zu umgehen, senden Sie kleinere Nachrichten oder verwenden TransferMode.Buffered.  
  
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
    <!- ... -->   
  </system.serviceModel>  
```  
  
 Der folgende Codeausschnitt veranschaulicht, wie <xref:System.ServiceModel.NetHttpBinding> im Code hinzugefügt wird.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren von Bindungen für Dienste](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Duplexdienste](../../../../docs/framework/wcf/feature-details/duplex-services.md)
