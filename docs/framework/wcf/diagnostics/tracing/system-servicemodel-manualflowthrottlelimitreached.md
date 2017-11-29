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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 556afe035697ee35d7ba86185b5b768a645c32c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="f3559-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="f3559-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="f3559-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="f3559-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="f3559-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3559-104">Description</span></span>  
 <span data-ttu-id="f3559-105">Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht.</span><span class="sxs-lookup"><span data-stu-id="f3559-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="f3559-106">Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f3559-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="f3559-107">Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="f3559-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="f3559-108">Eine spätere Änderung auf 0 (null) wird nicht verfolgt.</span><span class="sxs-lookup"><span data-stu-id="f3559-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="f3559-109">Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.</span><span class="sxs-lookup"><span data-stu-id="f3559-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3559-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3559-110">See Also</span></span>  
 [<span data-ttu-id="f3559-111">Ereignisablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="f3559-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="f3559-112">Verwenden der Ablaufverfolgung beheben</span><span class="sxs-lookup"><span data-stu-id="f3559-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="f3559-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="f3559-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
