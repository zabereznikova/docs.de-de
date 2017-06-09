---
title: "Verf&#252;gbarmachen der Daten als Dienst (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Erste Schritte, WCF Data Services"
  - "WCF Data Services, Konfigurieren"
  - "WCF Data Services, Erste Schritte"
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Verf&#252;gbarmachen der Daten als Dienst (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ist in Visual Studio integriert, um Ihnen das Definieren von Diensten zum Verfügbarmachen von Daten als [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feeds zu erleichtern.  Das Erstellen eines Datendiensts, der einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feed verfügbar macht, schließt die folgenden grundlegenden Schritte ein:  
  
1.  **Definieren** **des Datenmodells**.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] bietet eine systemeigene Unterstützung für Datenmodelle, die auf dem [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) basieren.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET Entity Framework\-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt außerdem Datenmodelle, die auf CLR \(Common Language Runtime\)\-Objekten basieren, die eine Instanz der <xref:System.Linq.IQueryable%601>\-Schnittstelle zurückgeben.  Dies ermöglicht es Ihnen, Datendienste bereitzustellen, die auf Listen, Arrays und Auflistungen in .NET Framework basieren. Zum Aktivieren von Erstellungs\-, Update\- und Löschvorgängen für diese Datenstrukturen müssen Sie außerdem die <xref:System.Data.Services.IUpdatable>\-Schnittstelle implementieren.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines Datendiensts mithilfe des Reflektionsanbieters](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
     Für erweiterte Szenarien umfasst [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] eine Reihe von Anbietern, die es Ihnen ermöglichen, ein Datenmodell auf der Grundlage spät gebundener Datentypen zu definieren.  Weitere Informationen finden Sie unter [Benutzerdefinierte Datendienstanbieter](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
2.  **Erstellen des Datendiensts** Der einfachste Datendienst macht eine Klasse, die von der <xref:System.Data.Services.DataService%601>\-Klasse erbt, mit einem Typ `T` verfügbar, bei dem es sich um den namespacequalifizierten Namen des Entitätscontainers handelt.  Weitere Informationen finden Sie unter [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Konfigurieren des Datendiensts.** Standardmäßig deaktiviert [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] den Zugriff auf von einem Entitätscontainer verfügbar gemachte Ressourcen. Die <xref:System.Data.Services.DataServiceConfiguration>\-Schnittstelle ermöglicht Ihnen das Konfigurieren des Zugriffs auf Ressourcen und Dienstvorgänge, das Angeben der unterstützten Version von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] und das Definieren von anderem dienstweiten Verhaltens wie das Batchverarbeitungsverhalten oder die maximale Anzahl von Entitäten, die in einer einzelnen Antwort zurückgegeben werden können. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Ein Beispiel zum Erstellen eines einfachen Datendiensts, der auf der Northwind\-Beispieldatenbank basiert, finden Sie unter [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [Übersicht](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)