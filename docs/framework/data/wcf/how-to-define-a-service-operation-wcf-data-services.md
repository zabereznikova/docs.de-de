---
title: 'Gewusst wie: Definieren eines Dienstvorgangs (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: e9d15698c1e020f5b4179efb3e8492f3754ff02f
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569126"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="67320-102">Gewusst wie: Definieren eines Dienstvorgangs (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="67320-102">How to: Define a Service Operation (WCF Data Services)</span></span>

<span data-ttu-id="67320-103">WCF Data Services Methoden verfügbar machen, die auf dem Server als Dienst Vorgänge definiert sind.</span><span class="sxs-lookup"><span data-stu-id="67320-103">WCF Data Services expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="67320-104">Dienst Vorgänge ermöglichen einem Datendienst, den Zugriff über einen URI auf eine Methode bereitzustellen, die auf dem Server definiert ist.</span><span class="sxs-lookup"><span data-stu-id="67320-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="67320-105">Um einen Dienst Vorgang zu definieren, wenden Sie das Attribut [`WebGet]` oder `[WebInvoke]` auf die Methode an.</span><span class="sxs-lookup"><span data-stu-id="67320-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="67320-106">Um Abfrage Operatoren zu unterstützen, muss der Dienst Vorgang eine <xref:System.Linq.IQueryable%601> Instanz zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="67320-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="67320-107">Dienstvorgänge können unter Umständen über die <xref:System.Data.Services.DataService%601.CurrentDataSource%2A>-Eigenschaft für den <xref:System.Data.Services.DataService%601> auf die zugrunde liegende Datenquelle zugreifen.</span><span class="sxs-lookup"><span data-stu-id="67320-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="67320-108">Weitere Informationen finden Sie unter [Dienst Vorgänge](service-operations-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="67320-108">For more information, see [Service Operations](service-operations-wcf-data-services.md).</span></span>

<span data-ttu-id="67320-109">Im Beispiel in diesem Thema wird ein Dienstvorgang mit dem Namen `GetOrdersByCity` definiert, der eine gefilterte <xref:System.Linq.IQueryable%601>-Instanz des `Orders`-Objekts und des verknüpften `Order_Details`-Objekts zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67320-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="67320-110">Im Beispiel wird auf die <xref:System.Data.Objects.ObjectContext>-Instanz zugegriffen, die die Datenquelle für den Northwind-Beispieldatendienst ist.</span><span class="sxs-lookup"><span data-stu-id="67320-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="67320-111">Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.</span><span class="sxs-lookup"><span data-stu-id="67320-111">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span>

### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="67320-112">So definieren Sie einen Dienstvorgang im Northwind-Datendienst</span><span class="sxs-lookup"><span data-stu-id="67320-112">To define a service operation in the Northwind data service</span></span>

1. <span data-ttu-id="67320-113">Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.</span><span class="sxs-lookup"><span data-stu-id="67320-113">In the Northwind data service project, open the Northwind.svc file.</span></span>

2. <span data-ttu-id="67320-114">Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `GetOrdersByCity` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="67320-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>

     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

3. <span data-ttu-id="67320-115">Fügen Sie in der `InitializeService`-Methode der `Northwind`-Klasse den folgenden Code hinzu, um den Zugriff auf den Dienstvorgang zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="67320-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>

     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="67320-116">So fragen Sie den GetOrdersByCity-Dienstvorgang ab</span><span class="sxs-lookup"><span data-stu-id="67320-116">To query the GetOrdersByCity service operation</span></span>

- <span data-ttu-id="67320-117">Geben Sie in einem Webbrowser einen der folgenden URIs ein, um den Dienstvorgang aufzurufen, der im folgenden Beispiel definiert wird:</span><span class="sxs-lookup"><span data-stu-id="67320-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`

## <a name="example"></a><span data-ttu-id="67320-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67320-118">Example</span></span>

<span data-ttu-id="67320-119">Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen `GetOrderByCity` im Northwind-Datendienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="67320-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="67320-120">In diesem Vorgang wird ADO.NET Entity Framework verwendet, um eine Reihe von `Orders`-Objekten und verknüpften `Order_Details`-Objekten als <xref:System.Linq.IQueryable%601>-Instanz basierend auf dem angegebenen Namen der Stadt zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="67320-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>

> [!NOTE]
> <span data-ttu-id="67320-121">Abfrageoperatoren werden an diesem Dienstvorgangsendpunkt unterstützt, da die Methode eine <xref:System.Linq.IQueryable%601>-Instanz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="67320-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>

[!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperation)]
[!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperation)]

## <a name="see-also"></a><span data-ttu-id="67320-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67320-122">See also</span></span>

- [<span data-ttu-id="67320-123">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="67320-123">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
