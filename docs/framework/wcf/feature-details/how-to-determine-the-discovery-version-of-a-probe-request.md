---
title: 'Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 98dfd5ec5d3c180b619e2f15d95037feae8ebbaf
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48031574"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="7f147-102">Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung</span><span class="sxs-lookup"><span data-stu-id="7f147-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="7f147-103">Ein Discovery-Proxy kann mehrere Discovery-Endpunkte mit unterschiedlichen Discovery-Versionen verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="7f147-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="7f147-104">Wenn eine UDP-Multicastüberprüfungsanforderung beim Proxy eingeht, sollte der Proxy mit einer Multicastunterdrückungsnachricht antworten.</span><span class="sxs-lookup"><span data-stu-id="7f147-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="7f147-105">Dazu müssen Sie die Discovery-Version der Anforderung kennen.</span><span class="sxs-lookup"><span data-stu-id="7f147-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="7f147-106">So bestimmen Sie die Discovery-Version einer Überprüfungsanforderung</span><span class="sxs-lookup"><span data-stu-id="7f147-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1.  <span data-ttu-id="7f147-107">Verwenden Sie wie im folgenden Code gezeigt in der Methode, die auf eine Überprüfungsanforderung antwortet (z. B. <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>), die statische <xref:System.ServiceModel.OperationContext.Current%2A>-Eigenschaft, um nach einer <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7f147-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7f147-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f147-108">See Also</span></span>  

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
- [<span data-ttu-id="7f147-109">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="7f147-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  