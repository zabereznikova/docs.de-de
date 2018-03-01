---
title: "Gewusst wie: Aktivieren von Paging für Datendienstergebnisse (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b03dd234681d031361696108702a7bbb558065ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="2af4c-102">Gewusst wie: Aktivieren von Paging für Datendienstergebnisse (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="2af4c-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="2af4c-103"> ermöglicht es Ihnen, die Anzahl der Entitäten einzuschränken, die von einer Datendienstabfrage zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2af4c-103"> enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="2af4c-104">Seitengrenzen werden in der Methode definiert, die zur Initialisierung des Diensts aufgerufen wird. Sie können für jede Entitätenmenge getrennt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2af4c-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="2af4c-105">Wenn Paging aktiviert ist, enthält der abschließende Eintrag im Feed einen Link zur nächsten Seite mit Daten.</span><span class="sxs-lookup"><span data-stu-id="2af4c-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="2af4c-106">Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2af4c-106">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="2af4c-107">Dieses Thema zeigt, wie ein Datendienst geändert werden muss, um das Paging für die zurückgegebenen `Customers`- und `Orders`-Entitätenmengen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2af4c-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="2af4c-108">In dem Beispiel in diesem Thema wird der Northwind-Beispieldatendienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="2af4c-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="2af4c-109">Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2af4c-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="2af4c-110">So aktivieren Sie das Paging für die zurückgegebenen Customers- und Orders-Entitätenmengen</span><span class="sxs-lookup"><span data-stu-id="2af4c-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
-   <span data-ttu-id="2af4c-111">Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2af4c-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="2af4c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2af4c-112">See Also</span></span>  
 [<span data-ttu-id="2af4c-113">Laden von verzögerten Inhalten</span><span class="sxs-lookup"><span data-stu-id="2af4c-113">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 [<span data-ttu-id="2af4c-114">Vorgehensweise: Laden von ausgelagerten Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="2af4c-114">How to: Load Paged Results</span></span>](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
