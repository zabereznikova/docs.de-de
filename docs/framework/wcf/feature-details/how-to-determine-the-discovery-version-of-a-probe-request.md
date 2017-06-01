---
title: "Vorgehensweise: Bestimmen der Discovery-Version einer &#220;berpr&#252;fungsanforderung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Vorgehensweise: Bestimmen der Discovery-Version einer &#220;berpr&#252;fungsanforderung
Ein Discovery\-Proxy kann mehrere Discovery\-Endpunkte mit unterschiedlichen Discovery\-Versionen verfügbar machen.  Wenn eine UDP\-Multicastüberprüfungsanforderung beim Proxy eingeht, sollte der Proxy mit einer Multicastunterdrückungsnachricht antworten.  Dazu müssen Sie die Discovery\-Version der Anforderung kennen.  
  
### So bestimmen Sie die Discovery\-Version einer Überprüfungsanforderung  
  
1.  Verwenden Sie wie im folgenden Code gezeigt in der Methode, die auf eine Überprüfungsanforderung antwortet \(z. B. <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>\), die statische <xref:System.ServiceModel.OperationContext.Current%2A>\-Eigenschaft, um nach einer <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> zu suchen.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
  
    ```  
  
## Siehe auch  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>   
 [Implementieren eines Suchproxys](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)   
 [Suchproxy\-Beispiel](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)