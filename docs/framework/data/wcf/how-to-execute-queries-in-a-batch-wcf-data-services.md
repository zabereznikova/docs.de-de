---
title: 'Gewusst wie: Ausführen von Abfragen in einem Batch (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
ms.openlocfilehash: 0ddf5b4f68ca08fca0c55cfcdfcd5431bcec6de2
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569052"
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Gewusst wie: Ausführen von Abfragen in einem Batch (WCF Data Services)
Mithilfe der WCF Data Services-Client Bibliothek können Sie mehr als eine Abfrage für den Datendienst in einem einzelnen Batch ausführen. Weitere Informationen finden Sie unter [Batch-Vorgänge](batching-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>-Methode zum Ausführen eines Arrays von <xref:System.Data.Services.Client.DataServiceRequest%601>-Objekten aufgerufen wird, das Abfragen enthält, die das `Customers`-Objekt und das `Products`-Objekt aus dem Northwind-Datendienst zurückgeben. Die Auflistung von <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekten in der zurückgegebenen <xref:System.Data.Services.Client.DataServiceResponse> wird aufgelistet, und die Auflistung von in jeder <xref:System.Data.Services.Client.QueryOperationResponse%601> enthaltenen Objekten wird ebenfalls aufgelistet.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
