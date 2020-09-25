---
title: 'Gewusst wie: Abfangen von Datendienstnachrichten (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: 8cc8bdcf776befafba967ee2649a6ada789d07c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194361"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a>Gewusst wie: Abfangen von Datendienstnachrichten (WCF Data Services)

Mit WCF Data Services können Sie Anforderungs Nachrichten abfangen, damit Sie einem Vorgang benutzerdefinierte Logik hinzufügen können. Zum Abfangen einer Nachricht verwenden Sie besonders attributierte Methoden im Datendienst. Weitere Informationen finden Sie unter [Interceptors](interceptors-wcf-data-services.md).  
  
 In dem Beispiel in diesem Thema wird der Northwind-Beispieldatendienst verwendet. Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a>So definieren Sie einen Abfrage-Interceptor für die "Orders"-Entitätenmenge  
  
1. Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.  
  
2. Fügen Sie der Codepage für die `Northwind`-Klasse die folgende `using`-Anweisung hinzu (`Imports` in Visual Basic).  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `OnQueryOrders` wie folgt:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a>So definieren Sie einen Change-Interceptor für die "Products"-Entitätenmenge  
  
1. Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.  
  
2. Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `OnChangeProducts` wie folgt:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird eine Abfrage-Interceptor-Methode für die `Orders`-Entitätenmenge definiert, die einen Lambda-Ausdruck zurückgibt. Dieser Ausdruck enthält einen Delegaten, der die angeforderten `Orders` auf Grundlage verknüpfter `Customers` filtert, die einen bestimmten Kontaktnamen haben. Der Name wird wiederum auf Grundlage des anfordernden Benutzers bestimmt. In diesem Beispiel wird davon ausgegangen, dass der Datendienst innerhalb einer ASP.NET-Webanwendung gehostet wird, die WCF verwendet, und dass die Authentifizierung aktiviert ist. Die <xref:System.Web.HttpContext>-Klasse wird verwendet, um das Prinzip der aktuellen Anforderung abzurufen.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird eine Change-Interceptor-Methode für die `Products`-Entitätenmenge definiert. Diese Methode überprüft die Eingabe an den Dienst für einen <xref:System.Data.Services.UpdateOperations.Add>-Vorgang oder <xref:System.Data.Services.UpdateOperations.Change>-Vorgang und löst eine Ausnahme aus, wenn eine Änderung an einem ausgelaufenen Produkt vorgenommen wird. Sie blockiert außerdem das Löschen von Produkten als nicht unterstützten Vorgang.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Definieren eines Dienstvorgangs](how-to-define-a-service-operation-wcf-data-services.md)
- [Definieren von WCF Data Services](defining-wcf-data-services.md)
