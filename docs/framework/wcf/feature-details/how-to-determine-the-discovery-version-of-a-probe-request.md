---
title: 'Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung'
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 98dfd5ec5d3c180b619e2f15d95037feae8ebbaf
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47400685"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung
Ein Discovery-Proxy kann mehrere Discovery-Endpunkte mit unterschiedlichen Discovery-Versionen verfügbar machen. Wenn eine UDP-Multicastüberprüfungsanforderung beim Proxy eingeht, sollte der Proxy mit einer Multicastunterdrückungsnachricht antworten. Dazu müssen Sie die Discovery-Version der Anforderung kennen.  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a>So bestimmen Sie die Discovery-Version einer Überprüfungsanforderung  
  
1.  Verwenden Sie wie im folgenden Code gezeigt in der Methode, die auf eine Überprüfungsanforderung antwortet (z. B. <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>), die statische <xref:System.ServiceModel.OperationContext.Current%2A>-Eigenschaft, um nach einer <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> zu suchen.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a>Siehe auch  

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
- [Implementieren eines Suchproxys](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  