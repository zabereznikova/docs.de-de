---
title: 'Vorgehensweise: Ausführen von Datendienstabfragen (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 62997821-e0c6-4c4d-9fb7-1273fb5e5d18
ms.openlocfilehash: 47943392ec6628b6d5a67ac333dd6793f35857b8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645673"
---
# <a name="how-to-execute-data-service-queries-wcf-data-services"></a>Vorgehensweise: Ausführen von Datendienstabfragen (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, mit den generierten Clientdatendienstklassen einen Datendienst aus einer .NET Framework-basierten Clientanwendung abzufragen. Für die Ausführung der Abfragen stehen folgende Methoden zur Verfügung:  
  
- Ausführen einer LINQ-Abfrage für die benannte <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz, die Sie aus dem <xref:System.Data.Services.Client.DataServiceContext>-Objekt abrufen, den das Tool `Add Data Service Reference` generiert.  
  
- Implizit durch Aufzählen über die benannte <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz, die Sie aus dem <xref:System.Data.Services.Client.DataServiceContext>-Objekt abrufen, den das Tool `Add Data Service Reference` generiert.  
  
- Explizit durch Aufrufen der <xref:System.Data.Services.Client.DataServiceContext.Execute%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceQuery%601>-Instanz oder der <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A>-Methode für die asynchrone Ausführung.  
  
 Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie eine LINQ-Abfrage definieren und ausführen, die alle `Customers` für den Northwind-Datendienst zurückgibt.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomerslinq)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomerslinq)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie den vom Tool `Add Data Service Reference` generierten Kontext verwenden, um eine Abfrage implizit auszuführen, die alle `Customers` für den Northwind-Datendienst zurückgibt. Der URI der angeforderten `Customers`-Entitätenmenge wird automatisch vom Kontext bestimmt. Die Abfrage wird implizit ausgeführt, wenn die Enumeration auftritt.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomers)]
 [!code-vb[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomers)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie den <xref:System.Data.Services.Client.DataServiceContext> verwenden, um eine Abfrage explizit auszuführen, die alle `Customers` für den Northwind-Datendienst zurückgibt.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomersexplicit)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomersexplicit)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Hinzufügen von Abfrageoptionen zu einer Datendienstabfrage](../../../../docs/framework/data/wcf/how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)
