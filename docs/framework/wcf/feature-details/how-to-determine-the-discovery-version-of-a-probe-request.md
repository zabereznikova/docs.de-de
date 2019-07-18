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
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung

Ein Discovery-Proxy kann mehrere Discovery-Endpunkte mit unterschiedlichen Discovery-Versionen verfügbar machen. Wenn eine UDP-multicast eingeht auf dem Proxy, der Proxy sollte mit einer multicastunterdrückungsnachricht Antworten. Zu diesem Zweck müssten sie die Discovery-Version der Anforderung kennen.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>So bestimmen Sie die Discovery-Version einer Überprüfungsanforderung

In der Methode, die auf eine überprüfungsanforderung antwortet (z. B. <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) verwenden Sie die statische <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> zu suchende Eigenschaft eine <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, wie im folgenden Code gezeigt.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementieren eines Suchproxys](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
