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
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="d0be2-102">Gewusst wie: Abfangen von Datendienstnachrichten (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="d0be2-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>

<span data-ttu-id="d0be2-103">Mit WCF Data Services können Sie Anforderungs Nachrichten abfangen, damit Sie einem Vorgang benutzerdefinierte Logik hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d0be2-103">With WCF Data Services, you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="d0be2-104">Zum Abfangen einer Nachricht verwenden Sie besonders attributierte Methoden im Datendienst.</span><span class="sxs-lookup"><span data-stu-id="d0be2-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="d0be2-105">Weitere Informationen finden Sie unter [Interceptors](interceptors-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d0be2-105">For more information, see [Interceptors](interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="d0be2-106">In dem Beispiel in diesem Thema wird der Northwind-Beispieldatendienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0be2-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="d0be2-107">Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.</span><span class="sxs-lookup"><span data-stu-id="d0be2-107">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="d0be2-108">So definieren Sie einen Abfrage-Interceptor für die "Orders"-Entitätenmenge</span><span class="sxs-lookup"><span data-stu-id="d0be2-108">To define a query interceptor for the Orders entity set</span></span>  
  
1. <span data-ttu-id="d0be2-109">Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="d0be2-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="d0be2-110">Fügen Sie der Codepage für die `Northwind`-Klasse die folgende `using`-Anweisung hinzu (`Imports` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d0be2-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. <span data-ttu-id="d0be2-111">Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `OnQueryOrders` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d0be2-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="d0be2-112">So definieren Sie einen Change-Interceptor für die "Products"-Entitätenmenge</span><span class="sxs-lookup"><span data-stu-id="d0be2-112">To define a change interceptor for the Products entity set</span></span>  
  
1. <span data-ttu-id="d0be2-113">Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="d0be2-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2. <span data-ttu-id="d0be2-114">Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `OnChangeProducts` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d0be2-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="d0be2-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0be2-115">Example</span></span>  

 <span data-ttu-id="d0be2-116">In diesem Beispiel wird eine Abfrage-Interceptor-Methode für die `Orders`-Entitätenmenge definiert, die einen Lambda-Ausdruck zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d0be2-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="d0be2-117">Dieser Ausdruck enthält einen Delegaten, der die angeforderten `Orders` auf Grundlage verknüpfter `Customers` filtert, die einen bestimmten Kontaktnamen haben.</span><span class="sxs-lookup"><span data-stu-id="d0be2-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="d0be2-118">Der Name wird wiederum auf Grundlage des anfordernden Benutzers bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d0be2-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="d0be2-119">In diesem Beispiel wird davon ausgegangen, dass der Datendienst innerhalb einer ASP.NET-Webanwendung gehostet wird, die WCF verwendet, und dass die Authentifizierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d0be2-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="d0be2-120">Die <xref:System.Web.HttpContext>-Klasse wird verwendet, um das Prinzip der aktuellen Anforderung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d0be2-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="d0be2-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0be2-121">Example</span></span>  

 <span data-ttu-id="d0be2-122">In diesem Beispiel wird eine Change-Interceptor-Methode für die `Products`-Entitätenmenge definiert.</span><span class="sxs-lookup"><span data-stu-id="d0be2-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="d0be2-123">Diese Methode überprüft die Eingabe an den Dienst für einen <xref:System.Data.Services.UpdateOperations.Add>-Vorgang oder <xref:System.Data.Services.UpdateOperations.Change>-Vorgang und löst eine Ausnahme aus, wenn eine Änderung an einem ausgelaufenen Produkt vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="d0be2-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="d0be2-124">Sie blockiert außerdem das Löschen von Produkten als nicht unterstützten Vorgang.</span><span class="sxs-lookup"><span data-stu-id="d0be2-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="d0be2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0be2-125">See also</span></span>

- [<span data-ttu-id="d0be2-126">Vorgehensweise: Definieren eines Dienstvorgangs</span><span class="sxs-lookup"><span data-stu-id="d0be2-126">How to: Define a Service Operation</span></span>](how-to-define-a-service-operation-wcf-data-services.md)
- [<span data-ttu-id="d0be2-127">Definieren von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d0be2-127">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
