---
title: 'Gewusst wie: Bestimmen der Anzahl von Entitäten, die von einer Abfrage zurückgegeben werden (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, row count
ms.assetid: 03d41a82-df95-40ac-8439-a6c327d37ba8
ms.openlocfilehash: 0513d7cdb3ab8de8cd8a73528f7e6038a0e4faed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194283"
---
# <a name="how-to-determine-the-number-of-entities-returned-by-a-query-wcf-data-services"></a>Gewusst wie: Bestimmen der Anzahl von Entitäten, die von einer Abfrage zurückgegeben werden (WCF Data Services)

Mit WCF Data Services können Sie die Anzahl der Entitäten ermitteln, die in der durch einen Abfrage-URI angegebenen Entitätenmenge liegen. Diese Anzahl kann entweder zusammen mit dem Abfrageergebnis oder als ganzzahliger Wert einbezogen werden. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird eine Abfrage ausgeführt, nachdem die <xref:System.Data.Services.Client.DataServiceQuery%601.IncludeTotalCount%2A>-Methode aufgerufen wurde. Die <xref:System.Data.Services.Client.QueryOperationResponse%601.TotalCount%2A>-Eigenschaft gibt die Anzahl der in der `Customers`-Entitätenmenge enthaltenen Entitäten zurück.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomers)]
 [!code-vb[Astoria Northwind Client#CountAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomers)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird die <xref:System.Linq.Enumerable.Count%2A>-Methode aufgerufen, um nur einen ganzzahligen Wert zurückzugeben, der die Anzahl der Entitäten in der `Customers`-Entitätenmenge angibt.  
  
 [!code-csharp[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#countallcustomersvalueonly)]
 [!code-vb[Astoria Northwind Client#CountAllCustomersValueOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#countallcustomersvalueonly)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)
