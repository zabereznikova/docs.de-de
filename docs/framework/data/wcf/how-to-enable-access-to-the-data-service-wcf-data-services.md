---
title: 'Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: eb9d7cd8e62a73f49fd2b0f2fc2572b01109553b
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44364371"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="d4f11-102">Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="d4f11-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="d4f11-103">In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] müssen Sie den Zugriff auf die von einem Datendienst verfügbar gemachten Ressourcen explizit gewähren.</span><span class="sxs-lookup"><span data-stu-id="d4f11-103">In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="d4f11-104">Daher müssen Sie nach der Erstellung eines neuen Datendiensts explizit den Zugriff auf einzelne Ressourcen als Entitätenmengen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d4f11-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="d4f11-105">In diesem Thema wird gezeigt, wie zu lesen und Schreibzugriff auf fünf Entitätenmengen im Northwind-Datendienst, der erstellt wird, wenn Sie abgeschlossen haben die [Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d4f11-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="d4f11-106">Da die <xref:System.Data.Services.EntitySetRights>-Enumeration mit dem <xref:System.FlagsAttribute> definiert wird, können Sie mehrere Berechtigungen für eine einzelne Entitätenmenge mithilfe eines logischen OR-Operators angeben.</span><span class="sxs-lookup"><span data-stu-id="d4f11-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4f11-107">Jeder Client, der auf die ASP.NET-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d4f11-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="d4f11-108">Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst schützen, um nicht autorisierten Zugriff auf Ressourcen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d4f11-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="d4f11-109">Weitere Informationen finden Sie unter [NIB: ASP.NET-Sicherheit](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span><span class="sxs-lookup"><span data-stu-id="d4f11-109">For more information, see [NIB: ASP.NET Security](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="d4f11-110">So aktivieren Sie den Zugriff auf den Datendienst</span><span class="sxs-lookup"><span data-stu-id="d4f11-110">To enable access to the data service</span></span>  
  
-   <span data-ttu-id="d4f11-111">Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d4f11-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="d4f11-112">Dies ermöglicht Clients, Lese- und Schreibzugriff auf die `Orders`-Entitätenmenge und die `Order_Details`-Entitätenmenge sowie Lesezugriff auf die `Customers`-Entitätenmenge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d4f11-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f11-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4f11-113">See Also</span></span>  
 [<span data-ttu-id="d4f11-114">Vorgehensweise: Entwickeln eines WCF-Datendiensts, der unter IIS ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="d4f11-114">How to: Develop a WCF Data Service Running on IIS</span></span>](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [<span data-ttu-id="d4f11-115">Konfigurieren des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="d4f11-115">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
