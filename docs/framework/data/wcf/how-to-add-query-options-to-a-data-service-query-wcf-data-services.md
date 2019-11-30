---
title: 'Gewusst wie: Hinzufügen von Abfrageoptionen zu einer Datendienstabfrage (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
ms.openlocfilehash: 7b5a9c15f2d46c89abf8fb5bc0f4be99e501a267
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569184"
---
# <a name="how-to-add-query-options-to-a-data-service-query-wcf-data-services"></a>Gewusst wie: Hinzufügen von Abfrageoptionen zu einer Datendienstabfrage (WCF Data Services)
WCF Data Services ermöglicht es Ihnen, mithilfe der generierten Client Datendienst Klassen einen Datendienst von einer .NET Framework basierten Client Anwendung abzufragen. Die einfachste Methode, dies zu tun, ist, einen Language Integrated Query (LINQ)-Abfrageausdruck zu verfassen, der die gewünschten Abfrageoptionen enthält. Sie können auch eine Reihe von LINQ fragt Methoden aufrufen, um eine entsprechende Abfrage zu verfassen. Schließlich können Sie mithilfe der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode einer Abfrage Abfrageoptionen hinzufügen. In jedem dieser Fälle enthält der vom Client erstellte URI die angeforderte Entitätenmenge, auf die die ausgewählten Abfrageoptionen angewendet wurden. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein LINQ-Abfrageausdruck verfasst wird, der nur Bestellungen mit Frachtkosten von mehr als 30 Dollar zurückgibt und die Ergebnisse in absteigender Reihenfolge nach dem Lieferdatum sortiert.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinq)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mithilfe von LINQ-Abfragemethoden eine LINQ-Abfrage verfasst wird, die der vorherigen Abfrage entspricht.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode verwendet wird, um eine <xref:System.Data.Services.Client.DataServiceQuery%601>-Abfrage zu erstellen, die den vorherigen Beispielen entspricht.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptions)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mit der `$orderby`-Abfrageoption zurückgegebene Orders-Objekte gefiltert und nach der Freight-Eigenschaft sortiert werden.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#orderwithfilter)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen des Datendiensts](querying-the-data-service-wcf-data-services.md)
- [Vorgehensweise: Projizieren von Abfrageergebnissen](how-to-project-query-results-wcf-data-services.md)
