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
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="9e23c-102">Verwenden einer benutzerdefinierten Bindung mit dem Suchclientchannel</span><span class="sxs-lookup"><span data-stu-id="9e23c-102">Using a Custom Binding with the Discovery Client Channel</span></span>

<span data-ttu-id="9e23c-103">Wenn Sie eine benutzerdefinierte Bindung mit <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> verwenden, müssen Sie ein <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>-Objekt definieren, das <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanzen erstellt.</span><span class="sxs-lookup"><span data-stu-id="9e23c-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="9e23c-104">Erstellen eines DiscoveryEndpointProvider-Objekts</span><span class="sxs-lookup"><span data-stu-id="9e23c-104">Creating a DiscoveryEndpointProvider</span></span>  

 <span data-ttu-id="9e23c-105">Der <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ist für die Bedarfs gesteuerte Erstellung von <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> Instanzen verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="9e23c-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="9e23c-106">Um einen Suchendpunktanbieter zu definieren, leiten Sie eine Klasse von <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ab, überschreiben die <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>-Methode und geben einen neuen Suchendpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="9e23c-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="9e23c-107">Das folgende Beispiel zeigt, wie Sie einen Suchendpunktanbieter erstellen.</span><span class="sxs-lookup"><span data-stu-id="9e23c-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
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
  
 <span data-ttu-id="9e23c-108">Sobald Sie den Suchendpunktanbieter definiert haben, können Sie eine benutzerdefinierte Bindung erstellen und das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> hinzufügen, das auf den Suchendpunktanbieter verweist. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9e23c-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="9e23c-109">Weitere Informationen zur Verwendung des Discovery-Client Kanals finden Sie unter [Verwenden des Ermittlungs Client Kanals](using-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="9e23c-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](using-the-discovery-client-channel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e23c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e23c-110">See also</span></span>

- [<span data-ttu-id="9e23c-111">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="9e23c-111">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="9e23c-112">Verwenden des Suchclientchannels</span><span class="sxs-lookup"><span data-stu-id="9e23c-112">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)
