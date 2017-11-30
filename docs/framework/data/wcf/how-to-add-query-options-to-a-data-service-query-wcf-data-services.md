---
title: "Gewusst wie: Hinzufügen von Abfrageoptionen zu einer Datendienstabfrage (WCF Data Services)"
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
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 95b77f1326c9a1d3522ed88fa5de9d1538b6efac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-query-options-to-a-data-service-query-wcf-data-services"></a>Gewusst wie: Hinzufügen von Abfrageoptionen zu einer Datendienstabfrage (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, mit den generierten Clientdatendienstklassen einen Datendienst aus einer .NET Framework-basierten Clientanwendung abzufragen. Die einfachste Methode, dies zu tun, ist, einen Language Integrated Query (LINQ)-Abfrageausdruck zu verfassen, der die gewünschten Abfrageoptionen enthält. Sie können auch eine Reihe von LINQ fragt Methoden aufrufen, um eine entsprechende Abfrage zu verfassen. Schließlich können Sie mithilfe der <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode einer Abfrage Abfrageoptionen hinzufügen. In jedem dieser Fälle enthält der vom Client erstellte URI die angeforderte Entitätenmenge, auf die die ausgewählten Abfrageoptionen angewendet wurden. Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein LINQ-Abfrageausdruck verfasst wird, der nur Bestellungen mit Frachtkosten von mehr als 30 Dollar zurückgibt und die Ergebnisse in absteigender Reihenfolge nach dem Lieferdatum sortiert.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinq)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mithilfe von LINQ-Abfragemethoden eine LINQ-Abfrage verfasst wird, die der vorherigen Abfrage entspricht.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A>-Methode verwendet wird, um eine <xref:System.Data.Services.Client.DataServiceQuery%601>-Abfrage zu erstellen, die den vorherigen Beispielen entspricht.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addqueryoptions)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mit der `$orderby`-Abfrageoption zurückgegebene Orders-Objekte gefiltert und nach der Freight-Eigenschaft sortiert werden.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#orderwithfilter)]  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 [Vorgehensweise: Projizieren von Abfrageergebnissen](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)
