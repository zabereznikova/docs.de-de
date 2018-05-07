---
title: 'Gewusst wie: Laden von verbundenen Entitäten (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: f7aa13ac217d86be23d0957ddb6c069831cacd2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Gewusst wie: Laden von verbundenen Entitäten (WCF Data Services)
Wenn Sie zugeordnete Entitäten in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] laden müssen, können Sie die <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceContext>-Klasse verwenden. Sie können auch die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> Methode auf die <xref:System.Data.Services.Client.DataServiceQuery%601> anfordern, dass die verknüpfte Entitäten vorzeitig in die gleiche Abfrageantwort geladen werden.  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der `Customer`, der sich auf jede zurückgegebene `Orders`-Instanz bezieht, explizit geladen wird.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode verwendet wird, um `Order Details` zurückzugeben, die zu den von der Abfrage zurückgegebenen `Orders` gehören.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
