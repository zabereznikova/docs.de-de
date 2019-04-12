---
title: 'Vorgehensweise: Bestimmen der Anzahl von Entitäten, die von einer Abfrage (WCF Data Services) zurückgegeben werden.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
ms.openlocfilehash: f723d91dd30817f6e15be11dd1bc1432a5939647
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517550"
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>Vorgehensweise: Bestimmen der Anzahl von Entitäten, die von einer Abfrage (WCF Data Services) zurückgegeben werden.
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie die Anzahl von Entitäten bestimmen, die in der durch einen Abfrage-URI angegebenen Entitätenmenge enthalten sind. Diese Anzahl kann entweder zusammen mit dem Abfrageergebnis oder als ganzzahliger Wert einbezogen werden. Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Abfrage ausgeführt, nachdem die <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>-Methode aufgerufen wurde. Die <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>-Eigenschaft gibt die Anzahl der in der `Customers`-Entitätenmenge enthaltenen Entitäten zurück.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>-Methode aufgerufen, um nur einen ganzzahligen Wert zurückzugeben, der die Anzahl der Entitäten in der `Customers`-Entitätenmenge angibt.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
