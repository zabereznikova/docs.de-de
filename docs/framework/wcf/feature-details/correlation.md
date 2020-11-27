---
title: Correlation
ms.date: 03/30/2017
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
ms.openlocfilehash: 1a357dd9469d7428af56772d3241e59766429990
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286772"
---
# <a name="correlation"></a><span data-ttu-id="a7aa9-102">Correlation</span><span class="sxs-lookup"><span data-stu-id="a7aa9-102">Correlation</span></span>

<span data-ttu-id="a7aa9-103">Wenn Workflowdienstanwendungen mit anderen Diensten kommunizieren, ist es wichtig, dass ausgetauschte Nachrichten an die richtige Workflowinstanz weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="a7aa9-104">Die Korrelation stellt den Mechanismus dafür bereit.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="a7aa9-105">Die Themen in diesem Abschnitt bieten eine Übersicht über die Korrelation und ihre Verwendung in unterschiedlichen Workflowdienstszenarien.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7aa9-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a7aa9-106">In This Section</span></span>  

 [<span data-ttu-id="a7aa9-107">Übersicht über die Korrelation</span><span class="sxs-lookup"><span data-stu-id="a7aa9-107">Correlation Overview</span></span>](correlation-overview.md)  
 <span data-ttu-id="a7aa9-108">Bietet eine Übersicht über die Korrelationstypen, die in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="a7aa9-109">Permanenter Duplex</span><span class="sxs-lookup"><span data-stu-id="a7aa9-109">Durable Duplex</span></span>](durable-duplex-correlation.md)  
 <span data-ttu-id="a7aa9-110">Beschreibt die permanente Duplexkorrelation.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-110">Describes durable duplex correlation.</span></span>
  
 [<span data-ttu-id="a7aa9-111">Anforderung-Antwort</span><span class="sxs-lookup"><span data-stu-id="a7aa9-111">Request-Reply</span></span>](request-reply-correlation.md)  
 <span data-ttu-id="a7aa9-112">Beschreibt die Anforderung/Antwort-Korrelation.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-112">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="a7aa9-113">Problembehandlung bei der Korrelation</span><span class="sxs-lookup"><span data-stu-id="a7aa9-113">Troubleshooting Correlation</span></span>](troubleshooting-correlation.md)  
 <span data-ttu-id="a7aa9-114">Stellt Methoden zum Beheben von Korrelationsproblemen bereit.</span><span class="sxs-lookup"><span data-stu-id="a7aa9-114">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7aa9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7aa9-115">See also</span></span>

- <xref:System.ServiceModel.Activities.CorrelationHandle>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.Receive>
- <xref:System.ServiceModel.CorrelationQuery>
