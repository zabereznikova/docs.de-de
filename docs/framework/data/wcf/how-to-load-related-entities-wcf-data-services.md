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
ms.openlocfilehash: 84c2448f317e813a95688feaaac1c97436de1b16
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569015"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Gewusst wie: Laden von verbundenen Entitäten (WCF Data Services)
Wenn Sie zugehörige Entitäten in WCF Data Services laden müssen, können Sie die <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceContext>-Klasse verwenden. Sie können auch die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceQuery%601> verwenden, um zu verlangen, dass verknüpfte Entitäten in derselben Abfrage Antwort eifrig geladen werden.  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie der `Customer`, der sich auf jede zurückgegebene `Orders`-Instanz bezieht, explizit geladen wird.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode verwendet wird, um `Order Details` zurückzugeben, die zu den von der Abfrage zurückgegebenen `Orders` gehören.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)
