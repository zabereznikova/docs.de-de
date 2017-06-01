---
title: "Gewusst wie: Laden von verkn&#252;pften Entit&#228;ten (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Verzögerte Inhalte"
  - "WCF Data Services, Laden von Daten"
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Laden von verkn&#252;pften Entit&#228;ten (WCF Data Services)
Wenn Sie zugeordnete Entitäten in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] laden müssen, können Sie die <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>\-Methode für die <xref:System.Data.Services.Client.DataServiceContext>\-Klasse verwenden.  Sie können auch die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>\-Methode für die <xref:System.Data.Services.Client.DataServiceQuery%601> verwenden, um festzulegen, dass verknüpfte Entitäten unverzüglich in die gleiche Abfrageantwort geladen werden.  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der `Customer`, der sich auf jede zurückgegebene `Orders`\-Instanz bezieht, explizit geladen wird.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung der <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>\-Methode verwendet wird, um `Order Details` zurückzugeben, die zu den von der Abfrage zurückgegebenen `Orders` gehören.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## Siehe auch  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)