---
title: Verwenden einer benutzerdefinierten Bindung mit dem Suchclientchannel
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: d84739a0021262826c541ab3ff9df663adabf44a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289658"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a>Verwenden einer benutzerdefinierten Bindung mit dem Suchclientchannel

Wenn Sie eine benutzerdefinierte Bindung mit <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> verwenden, müssen Sie ein <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>-Objekt definieren, das <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanzen erstellt.  
  
## <a name="creating-a-discoveryendpointprovider"></a>Erstellen eines DiscoveryEndpointProvider-Objekts  

 Der <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ist für die Bedarfs gesteuerte Erstellung von <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> Instanzen verantwortlich. Um einen Suchendpunktanbieter zu definieren, leiten Sie eine Klasse von <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ab, überschreiben die <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>-Methode und geben einen neuen Suchendpunkt zurück. Das folgende Beispiel zeigt, wie Sie einen Suchendpunktanbieter erstellen.  
  
```csharp
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 Sobald Sie den Suchendpunktanbieter definiert haben, können Sie eine benutzerdefinierte Bindung erstellen und das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> hinzufügen, das auf den Suchendpunktanbieter verweist. Dies wird im folgenden Beispiel veranschaulicht.  
  
```csharp
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 Weitere Informationen zur Verwendung des Discovery-Client Kanals finden Sie unter [Verwenden des Ermittlungs Client Kanals](using-the-discovery-client-channel.md).
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die WCF-Suche](wcf-discovery-overview.md)
- [Verwenden des Suchclientchannels](using-the-discovery-client-channel.md)
