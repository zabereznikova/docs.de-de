---
title: Verwenden einer benutzerdefinierten Bindung mit dem Suchclientchannel
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a5c80a257efb5f6006a0cf6394a1079cf92d2471
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="035f9-102">Verwenden einer benutzerdefinierten Bindung mit dem Suchclientchannel</span><span class="sxs-lookup"><span data-stu-id="035f9-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="035f9-103">Wenn Sie eine benutzerdefinierte Bindung mit <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> verwenden, müssen Sie ein <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>-Objekt definieren, das <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanzen erstellt.</span><span class="sxs-lookup"><span data-stu-id="035f9-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="035f9-104">Erstellen eines DiscoveryEndpointProvider-Objekts</span><span class="sxs-lookup"><span data-stu-id="035f9-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="035f9-105">Die <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ist verantwortlich für das Erstellen von <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> Instanzen bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="035f9-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="035f9-106">Um einen Suchendpunktanbieter zu definieren, leiten Sie eine Klasse von <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> ab, überschreiben die <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A>-Methode und geben einen neuen Suchendpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="035f9-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="035f9-107">Das folgende Beispiel zeigt, wie Sie einen Suchendpunktanbieter erstellen.</span><span class="sxs-lookup"><span data-stu-id="035f9-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
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
  
 <span data-ttu-id="035f9-108">Sobald Sie den Suchendpunktanbieter definiert haben, können Sie eine benutzerdefinierte Bindung erstellen und das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> hinzufügen, das auf den Suchendpunktanbieter verweist. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="035f9-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="035f9-109">Weitere Informationen zu den Discovery Clientchannel zu verwenden, finden Sie unter [mit der Discovery-Clientchannel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="035f9-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span></span> <span data-ttu-id="035f9-110">Ein vollständiges Codebeispiel finden Sie unter [Ermittlung Binding-Element-Beispiel](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)</span><span class="sxs-lookup"><span data-stu-id="035f9-110">For a complete code example, see [Discovery Binding Element Sample](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="035f9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="035f9-111">See Also</span></span>  
 [<span data-ttu-id="035f9-112">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="035f9-112">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="035f9-113">Verwenden des Ermittlungsclientkanals</span><span class="sxs-lookup"><span data-stu-id="035f9-113">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 [<span data-ttu-id="035f9-114">Beispiel für Ermittlungsbindungselement</span><span class="sxs-lookup"><span data-stu-id="035f9-114">Discovery Binding Element Sample</span></span>](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)
