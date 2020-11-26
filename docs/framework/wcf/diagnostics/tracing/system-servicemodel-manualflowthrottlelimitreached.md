---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: 180a06efc94acba40806e1f5d661553127549596
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248486"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="7f82b-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="7f82b-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>

<span data-ttu-id="7f82b-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="7f82b-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="7f82b-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7f82b-104">Description</span></span>  

 <span data-ttu-id="7f82b-105">Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht.</span><span class="sxs-lookup"><span data-stu-id="7f82b-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="7f82b-106">Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7f82b-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="7f82b-107">Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="7f82b-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="7f82b-108">Eine spätere Änderung auf 0 (null) wird nicht verfolgt.</span><span class="sxs-lookup"><span data-stu-id="7f82b-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="7f82b-109">Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.</span><span class="sxs-lookup"><span data-stu-id="7f82b-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f82b-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f82b-110">See also</span></span>

- [<span data-ttu-id="7f82b-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="7f82b-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="7f82b-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="7f82b-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="7f82b-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="7f82b-113">Administration and Diagnostics</span></span>](../index.md)
