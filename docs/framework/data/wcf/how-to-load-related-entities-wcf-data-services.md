---
title: 'Vorgehensweise: Zugehörige Entitäten laden (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: 14b0ba988c96c270610208a4f944083bb333eac5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780029"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Vorgehensweise: Zugehörige Entitäten laden (WCF Data Services)
Wenn Sie zugeordnete Entitäten in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] laden müssen, können Sie die <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceContext>-Klasse verwenden. Sie können auch die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> -Methode für die <xref:System.Data.Services.Client.DataServiceQuery%601> verwenden, um zu verlangen, dass verknüpfte Entitäten in derselben Abfrage Antwort eifrig geladen werden.  
  
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
