---
title: "Gewusst wie: Ausführen von Abfragen in einem Batch (WCF Data Services)"
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
helpviewer_keywords: WCF Data Services, batch requests
ms.assetid: 3b4db7df-bd33-43a1-8ea4-63a18e131f97
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d868881a3ff5c79f1f003881f58c726ebf25385e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-execute-queries-in-a-batch-wcf-data-services"></a>Gewusst wie: Ausführen von Abfragen in einem Batch (WCF Data Services)
Mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Clientbibliothek verwenden, können Sie mehr als eine Abfrage für den Datendienst in einem einzelnen Batch ausführen. Weitere Informationen finden Sie unter [Batchverarbeitungsvorgänge](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>-Methode zum Ausführen eines Arrays von <xref:System.Data.Services.Client.DataServiceRequest%601>-Objekten aufgerufen wird, das Abfragen enthält, die das `Customers`-Objekt und das `Products`-Objekt aus dem Northwind-Datendienst zurückgeben. Die Auflistung von <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekten in der zurückgegebenen <xref:System.Data.Services.Client.DataServiceResponse> wird aufgelistet, und die Auflistung von in jeder <xref:System.Data.Services.Client.QueryOperationResponse%601> enthaltenen Objekten wird ebenfalls aufgelistet.  
  
 [!code-csharp[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#batchquery)]
 [!code-vb[Astoria Northwind Client#BatchQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#batchquery)]  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
