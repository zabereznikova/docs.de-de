---
title: "Gewusst wie: Bestimmen der Anzahl von Entit&#228;ten, die von einer Abfrage zur&#252;ckgegeben werden (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Zeilenanzahl"
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Bestimmen der Anzahl von Entit&#228;ten, die von einer Abfrage zur&#252;ckgegeben werden (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie die Anzahl von Entitäten bestimmen, die in der durch einen Abfrage\-URI angegebenen Entitätenmenge enthalten sind.  Diese Anzahl kann entweder zusammen mit dem Abfrageergebnis oder als ganzzahliger Wert einbezogen werden.  Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 In diesem Beispiel wird eine Abfrage ausgeführt, nachdem die <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>\-Methode aufgerufen wurde.  Die <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>\-Eigenschaft gibt die Anzahl der in der `Customers`\-Entitätenmenge enthaltenen Entitäten zurück.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomers)]  
  
## Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>\-Methode aufgerufen, um nur einen ganzzahligen Wert zurückzugeben, der die Anzahl der Entitäten in der `Customers`\-Entitätenmenge angibt.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomersvalueonly)]  
  
## Siehe auch  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)