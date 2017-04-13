---
title: "Gewusst wie: Ausf&#252;hren von Abfragen in einem Batch (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Batchanforderungen"
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Ausf&#252;hren von Abfragen in einem Batch (WCF Data Services)
Mit der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliothek können Sie in einem einzigen Batch mehrere Abfragen für den Datendienst durchführen.  Weitere Informationen finden Sie unter [Batchverarbeitungsvorgänge](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:Microsoft.SqlServer.ReportingServices.ReportingService.ExecuteBatch%2A>\-Methode zum Ausführen eines Arrays von <xref:System.Data.Services.Client.DataServiceRequest%601>\-Objekten aufgerufen wird, das Abfragen enthält, die das `Customers`\-Objekt und das `Products`\-Objekt aus dem Northwind\-Datendienst zurückgeben.  Die Auflistung von <xref:System.Data.Services.Client.QueryOperationResponse%601>\-Objekten in der zurückgegebenen <xref:System.Data.Services.Client.DataServiceResponse> wird aufgelistet, und die Auflistung von in jeder <xref:System.Data.Services.Client.QueryOperationResponse%601> enthaltenen Objekten wird ebenfalls aufgelistet.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)