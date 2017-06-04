---
title: "Windows Communication Foundation-Endpunkte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Endpunkte [WCF]"
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Windows Communication Foundation-Endpunkte
Die gesamte Kommunikation mit einem [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienst verläuft über die *Endpunkte* des Diensts.  Endpunkte ermöglichen Clients den Zugriff auf die Funktionalität, die ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst anbietet.  
  
 Eine Übersicht über die Erstellung eines Endpunkts finden Sie unter [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md).  Jeder Endpunkt enthält Folgendes:  
  
-   Eine Adresse, die angibt, wo der Endpunkt zu finden ist.  
  
-   Eine Bindung, die angibt, wie ein Client mit dem Endpunkt kommunizieren kann.  
  
-   Ein Vertrag, der die verfügbaren Methoden identifiziert.  
  
 Beschreibungen, wie Sie diese einzelnen Teile eines Endpunkts angeben, finden Sie unter:  
  
-   [Angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [Entwerfen und Implementieren von Diensten](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## In diesem Abschnitt  
 [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 Beschreibt die Struktur eines Endpunkts und erläutert, wie Sie einen Endpunkt in einer Konfiguration oder im Code definieren und wie die Standardendpunkte, Bindungen und Verhalten von der Runtime bereitgestellt werden.  
  
 [Angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 Beschreibt, wie die Kommunikation mit einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst über Endpunkte erfolgt.  
  
 [Gewusst wie: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 Veranschaulicht, wie Sie einen Dienstendpunkt in einer Konfiguration erstellen.  
  
 [Gewusst wie: Erstellen eines Dienstendpunkts im Code](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 Veranschaulicht, wie Sie einen Dienstendpunkt im Code erstellen.  
  
 [Veröffentlichen von Metadatenendpunkten](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 Veranschaulicht, wie Sie Metadaten veröffentlichen, indem Sie Metadatenendpunkte in der Konfiguration und im Code veröffentlichen.  
  
## Referenz  
 <xref:System.ServiceModel.EndpointAddress>  
  
## Verwandte Abschnitte  
 [Grundlegender Programmierlebenszyklus](../../../docs/framework/wcf/basic-programming-lifecycle.md)