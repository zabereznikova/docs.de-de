---
title: "Gewusst wie: Ausführen von asynchronen Datendienstabfragen (WCF Data Services)"
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
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 86c38049f21ff6e9e02e1e715e6517c2947394e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Gewusst wie: Ausführen von asynchronen Datendienstabfragen (WCF Data Services)
Mit der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek können Sie Client/Server-Vorgänge wie das Ausführen von Abfragen und das Speichern von Änderungen asynchron ausführen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
>  In einer Anwendung, wo der Rückruf auf einem bestimmten Thread aufgerufen werden muss, müssen Sie explizites Marshalling der Ausführung der <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode durchführen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine asynchrone Abfrage durch Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode zum Starten der Abfrage ausgeführt wird. Der Inlinedelegat ruft die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode zum Anzeigen der Abfrageergebnisse auf.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
