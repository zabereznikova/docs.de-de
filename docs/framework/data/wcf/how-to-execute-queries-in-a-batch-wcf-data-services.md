---
title: 'Vorgehensweise: Ausführen von Abfragen in einem Batch (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: a825fe83ff62d935740fb69871ba2d1e2120e9ec
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790493"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Vorgehensweise: Ausführen von Abfragen in einem Batch (WCF Data Services)
Mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Client Bibliothek können Sie mehr als eine Abfrage für den Datendienst in einem einzelnen Batch ausführen. Weitere Informationen finden Sie unter [Batch-Vorgänge](batching-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>-Methode zum Ausführen eines Arrays von <xref:System.Data.Services.Client.DataServiceRequest%601>-Objekten aufgerufen wird, das Abfragen enthält, die das `Customers`-Objekt und das `Products`-Objekt aus dem Northwind-Datendienst zurückgeben. Die Auflistung von <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekten in der zurückgegebenen <xref:System.Data.Services.Client.DataServiceResponse> wird aufgelistet, und die Auflistung von in jeder <xref:System.Data.Services.Client.QueryOperationResponse%601> enthaltenen Objekten wird ebenfalls aufgelistet.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
