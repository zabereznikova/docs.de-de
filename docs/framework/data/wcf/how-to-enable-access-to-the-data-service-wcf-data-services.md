---
title: 'Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 377b031c48ed831cfa5e270426283ed03a55f886
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542306"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="29914-102">Vorgehensweise: Aktivieren des Zugriffs auf den Datendienst (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="29914-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="29914-103">In WCF Data Services müssen Sie explizit Zugriff auf die Ressourcen gewähren, die von einem Datendienst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="29914-103">In WCF Data Services, you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="29914-104">Daher müssen Sie nach der Erstellung eines neuen Datendiensts explizit den Zugriff auf einzelne Ressourcen als Entitätenmengen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="29914-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="29914-105">In diesem Thema wird gezeigt, wie Sie den Lese-und Schreibzugriff auf fünf der Entitätenmengen im Northwind-Datendienst aktivieren, der beim Abschluss des [Schnellstarts](quickstart-wcf-data-services.md)erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="29914-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="29914-106">Da die <xref:System.Data.Services.EntitySetRights>-Enumeration mit dem <xref:System.FlagsAttribute> definiert wird, können Sie mehrere Berechtigungen für eine einzelne Entitätenmenge mithilfe eines logischen OR-Operators angeben.</span><span class="sxs-lookup"><span data-stu-id="29914-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29914-107">Jeder Client, der auf die ASP.NET-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="29914-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="29914-108">Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst schützen, um nicht autorisierten Zugriff auf Ressourcen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="29914-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="29914-109">Weitere Informationen finden Sie unter [Sichern von ASP.NET Websites](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="29914-109">For more information, see [Securing ASP.NET Web Sites](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="29914-110">So aktivieren Sie den Zugriff auf den Datendienst</span><span class="sxs-lookup"><span data-stu-id="29914-110">To enable access to the data service</span></span>  
  
- <span data-ttu-id="29914-111">Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="29914-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="29914-112">Dies ermöglicht Clients, Lese- und Schreibzugriff auf die `Orders`-Entitätenmenge und die `Order_Details`-Entitätenmenge sowie Lesezugriff auf die `Customers`-Entitätenmenge zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="29914-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29914-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29914-113">See also</span></span>

- [<span data-ttu-id="29914-114">Vorgehensweise: Entwickeln eines mit IIS ausgeführten WCF-Datendiensts</span><span class="sxs-lookup"><span data-stu-id="29914-114">How to: Develop a WCF Data Service Running on IIS</span></span>](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [<span data-ttu-id="29914-115">Konfigurieren des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="29914-115">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
