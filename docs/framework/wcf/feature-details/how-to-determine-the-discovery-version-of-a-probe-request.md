---
title: "Vorgehensweise: Bestimmen der Discovery-Version einer Überprüfungsanforderung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2ff5d45997456c12d0292176771ad3c332f6c043
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [Implementieren eines Suchproxys](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [Suchproxybeispiel](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)
