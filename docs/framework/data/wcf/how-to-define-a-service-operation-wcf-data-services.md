---
title: 'Vorgehensweise: Definieren eines Dienstvorgangs (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: 75691a49624c179166d18225fac9fdc6c17a2308
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138098"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="549d5-102">Vorgehensweise: Definieren eines Dienstvorgangs (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="549d5-102">How to: Define a Service Operation (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] <span data-ttu-id="549d5-103">Machen Sie auf dem Server als Dienstvorgänge definierte Methoden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="549d5-103">expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="549d5-104">Dienstvorgänge ermöglichen einen Datendienst, der Zugriff über einen URI an eine Methode bereitzustellen, auf dem Server definiert sind.</span><span class="sxs-lookup"><span data-stu-id="549d5-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="549d5-105">Um einen Dienstvorgang zu definieren, gelten die [`WebGet]` oder `[WebInvoke]` -Attribut auf die Methode.</span><span class="sxs-lookup"><span data-stu-id="549d5-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="549d5-106">Um Abfrageoperatoren zu unterstützen, muss der Dienstvorgang Zurückgeben einer <xref:System.Linq.IQueryable%601> Instanz.</span><span class="sxs-lookup"><span data-stu-id="549d5-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="549d5-107">Dienstvorgänge können unter Umständen über die <xref:System.Data.Services.DataService%601.CurrentDataSource%2A>-Eigenschaft für den <xref:System.Data.Services.DataService%601> auf die zugrunde liegende Datenquelle zugreifen.</span><span class="sxs-lookup"><span data-stu-id="549d5-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="549d5-108">Weitere Informationen finden Sie unter [Dienstvorgänge](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="549d5-108">For more information, see [Service Operations](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="549d5-109">Im Beispiel in diesem Thema wird ein Dienstvorgang mit dem Namen `GetOrdersByCity` definiert, der eine gefilterte <xref:System.Linq.IQueryable%601>-Instanz des `Orders`-Objekts und des verknüpften `Order_Details`-Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="549d5-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="549d5-110">Im Beispiel wird auf die <xref:System.Data.Objects.ObjectContext>-Instanz zugegriffen, die die Datenquelle für den Northwind-Beispieldatendienst ist.</span><span class="sxs-lookup"><span data-stu-id="549d5-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="549d5-111">Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="549d5-111">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="549d5-112">So definieren Sie einen Dienstvorgang im Northwind-Datendienst</span><span class="sxs-lookup"><span data-stu-id="549d5-112">To define a service operation in the Northwind data service</span></span>  
  
1.  <span data-ttu-id="549d5-113">Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="549d5-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="549d5-114">Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `GetOrdersByCity` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="549d5-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  <span data-ttu-id="549d5-115">Fügen Sie in der `InitializeService`-Methode der `Northwind`-Klasse den folgenden Code hinzu, um den Zugriff auf den Dienstvorgang zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="549d5-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="549d5-116">So fragen Sie den GetOrdersByCity-Dienstvorgang ab</span><span class="sxs-lookup"><span data-stu-id="549d5-116">To query the GetOrdersByCity service operation</span></span>  
  
-   <span data-ttu-id="549d5-117">Geben Sie in einem Webbrowser einen der folgenden URIs ein, um den Dienstvorgang aufzurufen, der im folgenden Beispiel definiert wird:</span><span class="sxs-lookup"><span data-stu-id="549d5-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a><span data-ttu-id="549d5-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="549d5-118">Example</span></span>  
 <span data-ttu-id="549d5-119">Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen `GetOrderByCity` im Northwind-Datendienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="549d5-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="549d5-120">In diesem Vorgang wird ADO.NET Entity Framework verwendet, um eine Reihe von `Orders`-Objekten und verknüpften `Order_Details`-Objekten als <xref:System.Linq.IQueryable%601>-Instanz basierend auf dem angegebenen Namen der Stadt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="549d5-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="549d5-121">Abfrageoperatoren werden an diesem Dienstvorgangsendpunkt unterstützt, da die Methode eine <xref:System.Linq.IQueryable%601>-Instanz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="549d5-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a><span data-ttu-id="549d5-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="549d5-122">See also</span></span>

- [<span data-ttu-id="549d5-123">Definieren von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="549d5-123">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
