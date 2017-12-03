---
title: "Gewusst wie: Bestimmen der Anzahl von Entitäten, die von einer Abfrage zurückgegeben werden (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d8378cbf6f874e777ce03255962ea4c873449d7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>Gewusst wie: Bestimmen der Anzahl von Entitäten, die von einer Abfrage zurückgegeben werden (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie die Anzahl von Entitäten bestimmen, die in der durch einen Abfrage-URI angegebenen Entitätenmenge enthalten sind. Diese Anzahl kann entweder zusammen mit dem Abfrageergebnis oder als ganzzahliger Wert einbezogen werden. Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Abfrage ausgeführt, nachdem die <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>-Methode aufgerufen wurde. Die <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>-Eigenschaft gibt die Anzahl der in der `Customers`-Entitätenmenge enthaltenen Entitäten zurück.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>-Methode aufgerufen, um nur einen ganzzahligen Wert zurückzugeben, der die Anzahl der Entitäten in der `Customers`-Entitätenmenge angibt.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
