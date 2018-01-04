---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f149423fc8c0cd2a25834742d7c8b79ad8d8c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="d1da4-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d1da4-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="d1da4-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d1da4-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="d1da4-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1da4-104">Description</span></span>  
 <span data-ttu-id="d1da4-105">Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht.</span><span class="sxs-lookup"><span data-stu-id="d1da4-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="d1da4-106">Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d1da4-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="d1da4-107">Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="d1da4-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="d1da4-108">Eine spätere Änderung auf 0 (null) wird nicht verfolgt.</span><span class="sxs-lookup"><span data-stu-id="d1da4-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="d1da4-109">Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.</span><span class="sxs-lookup"><span data-stu-id="d1da4-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1da4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1da4-110">See Also</span></span>  
 [<span data-ttu-id="d1da4-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d1da4-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="d1da4-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="d1da4-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="d1da4-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="d1da4-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
