---
title: 'Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 2b7e42714ae1d16a84bcb6f0fc79cf5b376a7a16
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595413"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="c01bb-102">Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung</span><span class="sxs-lookup"><span data-stu-id="c01bb-102">How to:Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="c01bb-103">Ein Discovery-Proxy kann mehrere Discovery-Endpunkte mit unterschiedlichen Discovery-Versionen verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="c01bb-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="c01bb-104">Wenn eine UDP-Multicast Test Anforderung beim Proxy eintrifft, sollte der Proxy mit einer Multicast Unterdrückungs Meldung Antworten.</span><span class="sxs-lookup"><span data-stu-id="c01bb-104">When a UDP multicast Probe request arrives at the proxy, the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="c01bb-105">Um dies zu erreichen, muss die Ermittlungs Version der Anforderung bekannt sein.</span><span class="sxs-lookup"><span data-stu-id="c01bb-105">In order to do this, it would have to know the discovery version of the request.</span></span>

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="c01bb-106">So bestimmen Sie die Discovery-Version einer Überprüfungsanforderung</span><span class="sxs-lookup"><span data-stu-id="c01bb-106">To Determine the Discovery Version of a Probe Request</span></span>

<span data-ttu-id="c01bb-107">Verwenden Sie in der-Methode, die auf eine Test Anforderung antwortet (z <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> . b.), die statische- <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> Eigenschaft, um nach einem zu suchen <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c01bb-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) use the static <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, as shown in the following code.</span></span>

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a><span data-ttu-id="c01bb-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c01bb-108">See also</span></span>

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [<span data-ttu-id="c01bb-109">Implementieren eines Suchproxys</span><span class="sxs-lookup"><span data-stu-id="c01bb-109">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)
