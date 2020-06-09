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
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung

Ein Discovery-Proxy kann mehrere Discovery-Endpunkte mit unterschiedlichen Discovery-Versionen verfügbar machen. Wenn eine UDP-Multicast Test Anforderung beim Proxy eintrifft, sollte der Proxy mit einer Multicast Unterdrückungs Meldung Antworten. Um dies zu erreichen, muss die Ermittlungs Version der Anforderung bekannt sein.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>So bestimmen Sie die Discovery-Version einer Überprüfungsanforderung

Verwenden Sie in der-Methode, die auf eine Test Anforderung antwortet (z <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> . b.), die statische- <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> Eigenschaft, um nach einem zu suchen <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> , wie im folgenden Code gezeigt.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Implementieren eines Suchproxys](implementing-a-discovery-proxy.md)
