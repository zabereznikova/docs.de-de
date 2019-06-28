---
title: 'Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425270"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="ff4a4-102">Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung</span><span class="sxs-lookup"><span data-stu-id="ff4a4-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="ff4a4-103">Ein Discovery-Proxy kann mehrere Discovery-Endpunkte mit unterschiedlichen Discovery-Versionen verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="ff4a4-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="ff4a4-104">Wenn eine UDP-multicast eingeht auf dem Proxy, der Proxy sollte mit einer multicastunterdrückungsnachricht Antworten.</span><span class="sxs-lookup"><span data-stu-id="ff4a4-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="ff4a4-105">Zu diesem Zweck müssten sie die Discovery-Version der Anforderung kennen.</span><span class="sxs-lookup"><span data-stu-id="ff4a4-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="ff4a4-106">So bestimmen Sie die Discovery-Version einer Überprüfungsanforderung</span><span class="sxs-lookup"><span data-stu-id="ff4a4-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="ff4a4-107">In der Methode, die auf eine überprüfungsanforderung antwortet (z. B. <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) verwenden Sie die statische <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> zu suchende Eigenschaft eine <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff4a4-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="ff4a4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff4a4-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="ff4a4-109">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="ff4a4-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
