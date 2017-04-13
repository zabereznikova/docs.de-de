---
title: "Ver&#246;ffentlichen von Metadatenendpunkten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Ver&#246;ffentlichen von Metadatenendpunkten
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienste veröffentlichen Metadaten, indem sie einen oder mehrere Metadatenendpunkte veröffentlichen.Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS\-MetadataExchange \(MEX\) und HTTP\/GET\-Anforderungen.Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können.Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.  
  
## Inhalt dieses Abschnitts  
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 In diesem Abschnitt wird veranschaulicht, wie ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst für die Veröffentlichung von Metadaten konfiguriert wird, sodass Clients die Metadaten über WS\-MetadataExchange oder eine HTTP\/GET\-Anforderung mithilfe einer `?wsdl`\-Abfragezeichenfolge abrufen können.  
  
 [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst über den Code](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Metadatenveröffentlichung für einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst im Code aktiviert wird, sodass Clients Metadaten über WS\-MetadataExchange oder eine HTTP\/GET\-Anforderung mithilfe der `?wsdl`\-Abfragezeichenfolge abrufen können.  
  
## Siehe auch  
 [Veröffentlichen von Metadaten](../../../docs/framework/wcf/feature-details/publishing-metadata.md)