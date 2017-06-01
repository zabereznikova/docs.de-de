---
title: "Gewusst wie: Erstellen eines Datendiensts mithilfe des Reflektionsanbieters (WCF Data Services) | Microsoft Docs"
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
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Erstellen eines Datendiensts mithilfe des Reflektionsanbieters (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, ein auf beliebigen Klassen basierendes Datenmodell zu definieren, solange die Klassen als Objekte verfügbar gemacht werden, die die <xref:System.Linq.IQueryable%601>\-Schnittstelle implementieren.  Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
## Beispiel  
 Im folgenden Beispiel wird ein Datenmodell definiert, das `Orders` und `Items` enthält.  Die Entitätscontainerklasse `OrderItemData` enthält zwei öffentliche Methoden, die <xref:System.Linq.IQueryable%601>\-Schnittstellen zurückgeben.  Diese Schnittstellen sind die Entitätenmengen der Entitätstypen `Orders` und `Items`.  Eine `Order` kann mehrere `Items` enthalten, daher verfügt der `Orders`\-Entitätstyp über eine `Items`\-Navigationseigenschaft, die eine Auflistung von `Items`\-Objekten zurückgibt.  Die `OrderItemData`\-Entitätscontainerklasse ist der generische Typ der <xref:System.Data.Services.DataService%601>\-Klasse, von der der `OrderItems`\-Datendienst abgeleitet ist.  
  
> [!NOTE]
>  Da in diesem Beispiel ein Datenanbieter im Arbeitsspeicher veranschaulicht wird und Änderungen außerhalb der aktuellen Objektinstanzen nicht beibehalten werden, leitet sich aus der Implementierung der <xref:System.Data.Services.IUpdatable>\-Schnittstelle kein Vorteil ab.  Ein Beispiel, in dem die <xref:System.Data.Services.IUpdatable>\-Schnittstelle implementiert wird, finden Sie unter [Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL\-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## Siehe auch  
 [Gewusst wie: Erstellen eines Datendiensts mit einer LINQ to SQL\-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)   
 [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET Entity Framework\-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)