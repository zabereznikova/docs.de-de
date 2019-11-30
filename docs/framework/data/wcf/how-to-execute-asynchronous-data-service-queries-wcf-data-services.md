---
title: 'Gewusst wie: Ausführen von asynchronen Datendienstabfragen (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: 68e2035315780b7c6dd60e93ae6eb10d252aabb3
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569070"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Gewusst wie: Ausführen von asynchronen Datendienstabfragen (WCF Data Services)
Mithilfe der WCF Data Services-Client Bibliothek können Sie Client/Server-Vorgänge wie das Ausführen von Abfragen und das Speichern von Änderungen asynchron ausführen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
> In einer Anwendung, wo der Rückruf auf einem bestimmten Thread aufgerufen werden muss, müssen Sie explizites Marshalling der Ausführung der <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode durchführen. Weitere Informationen finden Sie unter [asynchrone Vorgänge](asynchronous-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine asynchrone Abfrage durch Aufrufen der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode zum Starten der Abfrage ausgeführt wird. Der Inlinedelegat ruft die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>-Methode zum Anzeigen der Abfrageergebnisse auf.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
