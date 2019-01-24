---
title: Verwenden einer benutzerdefinierten Bindung mit dem Suchclientchannel
ms.date: 03/30/2017
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
ms.openlocfilehash: 6fe9370bb22ca424774fc8cb4566e0802bc06697
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698358"
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="5818e-102">Verwenden einer benutzerdefinierten Bindung mit dem Suchclientchannel</span><span class="sxs-lookup"><span data-stu-id="5818e-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="5818e-103">Wenn Sie eine benutzerdefinierte Bindung mit <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> verwenden, müssen Sie ein <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>-Objekt definieren, das <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanzen erstellt.</span><span class="sxs-lookup"><span data-stu-id="5818e-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="5818e-104">Erstellen eines DiscoveryEndpointProvider-Objekts</span><span class="sxs-lookup"><span data-stu-id="5818e-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="5818e-105">Die <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ist verantwortlich für das Erstellen von <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> Instanzen bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5818e-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="5818e-106">Um einen Suchendpunktanbieter zu definieren, leiten Sie eine Klasse von <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ab, überschreiben die <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>-Methode und geben einen neuen Suchendpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="5818e-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="5818e-107">Das folgende Beispiel zeigt, wie Sie einen Suchendpunktanbieter erstellen.</span><span class="sxs-lookup"><span data-stu-id="5818e-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
```  
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
  
 <span data-ttu-id="5818e-108">Sobald Sie den Suchendpunktanbieter definiert haben, können Sie eine benutzerdefinierte Bindung erstellen und das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> hinzufügen, das auf den Suchendpunktanbieter verweist. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5818e-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 <span data-ttu-id="5818e-109">Weitere Informationen zur Verwendung von Discovery-Clientchannel finden Sie unter [mithilfe von Discovery-Clientchannel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="5818e-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5818e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5818e-110">See also</span></span>

- [<span data-ttu-id="5818e-111">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="5818e-111">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="5818e-112">Verwenden des Ermittlungsclientkanals</span><span class="sxs-lookup"><span data-stu-id="5818e-112">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
