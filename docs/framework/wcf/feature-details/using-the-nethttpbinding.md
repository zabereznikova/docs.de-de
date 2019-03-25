---
title: Verwenden der NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 47a4da6dd709c300b62a7380e6e0754e31782dd8
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58411069"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="67081-102">Verwenden der NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="67081-102">Using the NetHttpBinding</span></span>
<span data-ttu-id="67081-103"><xref:System.ServiceModel.NetHttpBinding> ist eine für die Nutzung von HTTP- oder WebSocket-Diensten entwickelte Bindung, die standardmäßig die binäre Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="67081-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="67081-104"><xref:System.ServiceModel.NetHttpBinding> erkennt, ob sie mit einem Anforderung-Antwort-Vertrag oder einem Duplexvertrag verwendet wird, und ändert das Verhalten entsprechend, indem HTTP für Anforderung-Antwort-Verträge und WebSockets für Duplexverträge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67081-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="67081-105">Dieses Verhalten kann mit der <xref:System.ServiceModel.Channels.WebSocketTransportUsage>-Einstellung überschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="67081-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <span data-ttu-id="67081-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> -Dies erzwingt die Verwendung von WebSockets sogar für Anforderung-Antwort-Verträgen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67081-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <span data-ttu-id="67081-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> – Dies verhindert, dass WebSockets verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67081-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> - This prevents WebSockets from being used.</span></span> <span data-ttu-id="67081-108">Der Versuch, einen Duplexvertrag mit dieser Einstellung zu verwenden, löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="67081-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <span data-ttu-id="67081-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> – Dies ist der Standardwert und verhält sich wie oben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="67081-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="67081-110"><xref:System.ServiceModel.NetHttpBinding> unterstützt zuverlässige Sitzungen im HTTP-Modus und WebSocket-Modus.</span><span class="sxs-lookup"><span data-stu-id="67081-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="67081-111">Im WebSocket-Modus werden Sitzungen vom Transport bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="67081-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="67081-112">Wenn <xref:System.ServiceModel.NetHttpBinding> verwendet wird und TransferMode für die Bindung auf TransferMode.Streamed festgelegt ist, verursachen große Datenströme ein Deadlock und der Aufruf ein Timeout.</span><span class="sxs-lookup"><span data-stu-id="67081-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="67081-113">Um dieses Problem zu umgehen, senden Sie kleinere Nachrichten oder verwenden TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="67081-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="67081-114">Konfigurieren eines Diensts für die Verwendung von "NetHttpBinding"</span><span class="sxs-lookup"><span data-stu-id="67081-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="67081-115">
  <xref:System.ServiceModel.NetHttpBinding> kann wie jede andere Bindung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="67081-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="67081-116">Der folgende Konfigurationsausschnitt veranschaulicht, wie ein WCF-Dienst mit <xref:System.ServiceModel.NetHttpBinding> konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="67081-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
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
  
 <span data-ttu-id="67081-117">Der folgende Codeausschnitt veranschaulicht, wie <xref:System.ServiceModel.NetHttpBinding> im Code hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="67081-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="67081-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67081-118">See also</span></span>
- [<span data-ttu-id="67081-119">Konfigurieren von Bindungen für Dienste</span><span class="sxs-lookup"><span data-stu-id="67081-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="67081-120">Bindungen</span><span class="sxs-lookup"><span data-stu-id="67081-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)
- [<span data-ttu-id="67081-121">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="67081-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="67081-122">Duplexdienste</span><span class="sxs-lookup"><span data-stu-id="67081-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
