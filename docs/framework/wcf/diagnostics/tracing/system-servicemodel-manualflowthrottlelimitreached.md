---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 86d47ab0a83ff3e4a68bfa8ccf1349cf2b345b23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597735"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="41510-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="41510-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="41510-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="41510-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="41510-104">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41510-104">Description</span></span>  
 <span data-ttu-id="41510-105">Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht.</span><span class="sxs-lookup"><span data-stu-id="41510-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="41510-106">Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="41510-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="41510-107">Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="41510-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="41510-108">Eine spätere Änderung auf 0 (null) wird nicht verfolgt.</span><span class="sxs-lookup"><span data-stu-id="41510-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="41510-109">Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.</span><span class="sxs-lookup"><span data-stu-id="41510-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41510-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41510-110">See also</span></span>
- [<span data-ttu-id="41510-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="41510-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="41510-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="41510-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="41510-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41510-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
