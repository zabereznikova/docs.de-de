---
title: "Verfügbarmachen der Daten als Dienst (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 122d05d5e4bd7690f32b22453dccbfaab2fb7f13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-your-data-as-a-service-wcf-data-services"></a>Verfügbarmachen der Daten als Dienst (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]integriert in Visual Studio für die Ihnen ermöglichen, Dienste, um das Verfügbarmachen von Daten als einfacher definieren [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feeds. Stellt einen Datendienst erstellen, die eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feed umfasst die folgenden grundlegenden Schritte:  
  
1.  **Definieren Sie** **Datenmodell**. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]systemintern unterstützt Datenmodelle für die auf der Basis der [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer Service unter Verwendung einer ADO.NET Entity Framework-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt außerdem Datenmodelle, die auf CLR (Common Language Runtime)-Objekten basieren, die eine Instanz der <xref:System.Linq.IQueryable%601>-Schnittstelle zurückgeben. Dies ermöglicht es Ihnen, Datendienste bereitzustellen, die auf Listen, Arrays und Auflistungen in .NET Framework basieren. Zum Aktivieren von Erstellungs-, Aktualisierungs- und Löschvorgängen für diese Datenstrukturen müssen Sie außerdem die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Daten mithilfe des Reflektionsanbieters](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
     Für komplexere Szenarios [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] umfasst eine Reihe von Anbietern, die Ihnen ermöglichen, ein Datenmodell basierend auf spät gebundener Datentypen zu definieren. Weitere Informationen finden Sie unter [Benutzerdefinierte Datendienstanbieter](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
2.  **Erstellen des Datendiensts.** Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601> -Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt. Weitere Informationen finden Sie unter [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Konfigurieren des Datendiensts.** Standardmäßig deaktiviert [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] den Zugriff auf die von einem Entitätscontainer verfügbar gemachten Ressourcen. Die <xref:System.Data.Services.DataServiceConfiguration>-Schnittstelle ermöglicht Ihnen das Konfigurieren des Zugriffs auf Ressourcen und Dienstvorgänge, das Angeben der unterstützten Version von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] und das Definieren anderer dienstweiter Verhalten, wie das Batchverarbeitungsverhalten oder die maximale Anzahl von Entitäten, die in einer einzelnen Antwort zurückgegeben werden können. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Ein Beispiel dafür, wie einen einfache Datendienst erstellen, die auf der Northwind-Beispieldatenbank basiert, finden Sie unter [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
