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
ms.openlocfilehash: 49b41e27847005c7187435229e030994df10df26
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="e6f9d-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="e6f9d-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="e6f9d-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="e6f9d-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="e6f9d-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6f9d-104">Description</span></span>  
 <span data-ttu-id="e6f9d-105">Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht.</span><span class="sxs-lookup"><span data-stu-id="e6f9d-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="e6f9d-106">Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e6f9d-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="e6f9d-107">Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="e6f9d-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="e6f9d-108">Eine spätere Änderung auf 0 (null) wird nicht verfolgt.</span><span class="sxs-lookup"><span data-stu-id="e6f9d-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="e6f9d-109">Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.</span><span class="sxs-lookup"><span data-stu-id="e6f9d-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f9d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6f9d-110">See Also</span></span>  
 [<span data-ttu-id="e6f9d-111">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e6f9d-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="e6f9d-112">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="e6f9d-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="e6f9d-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="e6f9d-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
