---
title: Korrelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc1608cc4e746af56e7d89237f0c1f5e6cc3bc7e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="correlation"></a><span data-ttu-id="9506e-102">Korrelation</span><span class="sxs-lookup"><span data-stu-id="9506e-102">Correlation</span></span>
<span data-ttu-id="9506e-103">Wenn Workflowdienstanwendungen mit anderen Diensten kommunizieren, ist es wichtig, dass ausgetauschte Nachrichten an die richtige Workflowinstanz weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="9506e-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="9506e-104">Die Korrelation stellt den Mechanismus dafür bereit.</span><span class="sxs-lookup"><span data-stu-id="9506e-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="9506e-105">Die Themen in diesem Abschnitt bieten eine Übersicht über die Korrelation und ihre Verwendung in unterschiedlichen Workflowdienstszenarien.</span><span class="sxs-lookup"><span data-stu-id="9506e-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9506e-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9506e-106">In This Section</span></span>  
 [<span data-ttu-id="9506e-107">Übersicht über die Korrelation</span><span class="sxs-lookup"><span data-stu-id="9506e-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="9506e-108">Bietet eine Übersicht über die Korrelationstypen, die in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9506e-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="9506e-109">Kontextaustausch</span><span class="sxs-lookup"><span data-stu-id="9506e-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="9506e-110">Beschreibt die Kontextaustauschkorrelation.</span><span class="sxs-lookup"><span data-stu-id="9506e-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="9506e-111">Permanenter Duplex</span><span class="sxs-lookup"><span data-stu-id="9506e-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="9506e-112">Beschreibt die permanente Duplexkorrelation.</span><span class="sxs-lookup"><span data-stu-id="9506e-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="9506e-113">Inhaltsbasiert</span><span class="sxs-lookup"><span data-stu-id="9506e-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="9506e-114">Beschreibt die inhaltsbasierte Korrelation.</span><span class="sxs-lookup"><span data-stu-id="9506e-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="9506e-115">Anforderung-Antwort</span><span class="sxs-lookup"><span data-stu-id="9506e-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="9506e-116">Beschreibt die Anforderung/Antwort-Korrelation.</span><span class="sxs-lookup"><span data-stu-id="9506e-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="9506e-117">Beheben von Korrelationsproblemen</span><span class="sxs-lookup"><span data-stu-id="9506e-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="9506e-118">Stellt Methoden zum Beheben von Korrelationsproblemen bereit.</span><span class="sxs-lookup"><span data-stu-id="9506e-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9506e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9506e-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="9506e-120">Inhaltsbasierte Korrelation</span><span class="sxs-lookup"><span data-stu-id="9506e-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="9506e-121">Korrelierter Rechner</span><span class="sxs-lookup"><span data-stu-id="9506e-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
