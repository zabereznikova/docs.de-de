---
title: 'Vorgehensweise: Ausführen von asynchronen Datendienstabfragen (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: afc12fc0965a8f6cffe1f214cae1a6d108c686d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621772"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Vorgehensweise: Ausführen von asynchronen Datendienstabfragen (WCF Data Services)
Mit der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Clientbibliothek können Sie Client/Server-Vorgänge wie das Ausführen von Abfragen und das Speichern von Änderungen asynchron ausführen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
>  In einer Anwendung, wo der Rückruf auf einem bestimmten Thread aufgerufen werden muss, müssen Sie explizites Marshalling der Ausführung der <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode durchführen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine asynchrone Abfrage durch Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode zum Starten der Abfrage ausgeführt wird. Der Inlinedelegat ruft die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode zum Anzeigen der Abfrageergebnisse auf.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Siehe auch
- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
