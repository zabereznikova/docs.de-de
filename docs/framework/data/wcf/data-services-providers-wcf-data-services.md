---
title: "Datendiensteanbieter (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Anbieter"
ms.assetid: a0160b1b-3d9c-4cc8-8391-cb0986a60a41
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Datendiensteanbieter (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt mehrere Anbietermodelle zum Verfügbarmachen von Daten als [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feed.  Dieses Thema enthält Informationen, um Ihnen die Auswahl des besten [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Anbieters für eine Datenquelle zu erleichtern.  
  
## Datenquellenanbieter  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt die folgenden Anbieter zur Definition des Datenmodells eines Datendiensts.  
  
|Anbieter|Beschreibung|  
|--------------|------------------|  
|Entity Framework\-Anbieter|Dieser Anbieter ermöglicht Ihnen mithilfe von ADO.NET Entity Framework, relationale Daten durch das Definieren eines Datenmodells, das relationalen Daten zugeordnet wird, mit einem Datendienst zu verwenden.  Die Datenquelle kann SQL Server oder eine beliebige andere Datenquelle mit Drittanbieterunterstützung für das Entity Framework sein.  Sie sollten den Entity Framework\-Anbieter verwenden, wenn Sie eine relationale Datenquelle wie eine SQL Server\-Datenbank verwenden.  Weitere Informationen finden Sie unter [Entity Framework\-Anbieter](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md).|  
|Reflektionsanbieter|Dieser Anbieter ermöglicht es Ihnen, mithilfe von Reflektion ein auf vorhandenen Datenklassen, die als Instanzen der <xref:System.Linq.IQueryable%601>\-Schnittstelle verfügbar gemacht werden können, basierendes Datenmodell zu definieren.  Updates werden durch Implementieren der <xref:System.Data.Services.IUpdatable>\-Schnittstelle aktiviert.  Verwenden Sie diesen Anbieter, wenn Sie zur Laufzeit definierte statische Datenklassen verwenden, z. B. durch LINQ to SQL generierte oder durch ein typisiertes DataSet definierte Datenklassen.  Weitere Informationen finden Sie unter [Reflektionsanbieter](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md).|  
|Benutzerdefinierte Datendienstanbieter|[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] umfasst eine Reihe von Anbietern, die es Ihnen ermöglichen, ein Datenmodell auf der Grundlage spät gebundener Datentypen dynamisch zu definieren.  Sie sollten diese Schnittstellen implementieren, wenn die verfügbar gemachten Daten beim Entwurf der Anwendung nicht bekannt sind oder wenn die Entity Framework\- oder Reflektionsanbieter nicht hinreichend sind.  Weitere Informationen finden Sie unter [Benutzerdefinierte Datendienstanbieter](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).|  
  
## Andere Datendienstanbieter  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügt über den folgenden zusätzlichen Datendienstanbieter, der die Leistung einer mit einem der anderen Anbieter definierten Datenquelle verbessert.  
  
|Anbieter|Beschreibung|  
|--------------|------------------|  
|Streaminganbieter|Dieser Anbieter ermöglicht es Ihnen, Binary Large Object\-Datentypen mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbar zu machen.  Ein Streaminganbieter wird durch Implementieren der <xref:System.Data.Services.Providers.IDataServiceStreamProvider>\-Schnittstelle erstellt.  Dieser Anbieter kann zusammen mit einem beliebigen Datenquellenanbieter implementiert werden.  Weitere Informationen finden Sie unter [Streaminganbieter](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
## Siehe auch  
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)   
 [Hosten des Datendiensts](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)