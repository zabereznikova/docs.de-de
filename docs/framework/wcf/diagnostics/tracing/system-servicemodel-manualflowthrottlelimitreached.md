---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.date: 03/30/2017
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
ms.openlocfilehash: bffa6361df5a50748f45aa3004f7a307ad516d7b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580488"
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a><span data-ttu-id="d6582-102">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d6582-102">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>
<span data-ttu-id="d6582-103">System.ServiceModel.ManualFlowThrottleLimitReached</span><span class="sxs-lookup"><span data-stu-id="d6582-103">System.ServiceModel.ManualFlowThrottleLimitReached</span></span>  
  
## <a name="description"></a><span data-ttu-id="d6582-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d6582-104">Description</span></span>  
 <span data-ttu-id="d6582-105">Das System hat den für die ManualFlowControlLimit-Drosselung festgelegten Grenzwert erreicht.</span><span class="sxs-lookup"><span data-stu-id="d6582-105">The system reached the limit set for the ManualFlowControlLimit throttle.</span></span> <span data-ttu-id="d6582-106">Der Drosselungswert kann geändert werden, indem die ManualFlowControlLimit-Eigenschaft nach Bedarf entweder auf ServiceHost oder InstanceContext festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="d6582-106">The throttle value can be changed by modifying the ManualFlowControlLimit property on either the ServiceHost or InstanceContext, as applicable.</span></span>  
  
 <span data-ttu-id="d6582-107">Diese Ablaufverfolgung wird ausgegeben, wenn die manuelle Flussteuerungsgrenze anfangs auf 0 (null) reduziert wird.</span><span class="sxs-lookup"><span data-stu-id="d6582-107">This trace is emitted when the manual flow control limit is initially reduced to 0.</span></span> <span data-ttu-id="d6582-108">Eine spätere Änderung auf 0 (null) wird nicht verfolgt.</span><span class="sxs-lookup"><span data-stu-id="d6582-108">Subsequent changes to 0 are not traced.</span></span> <span data-ttu-id="d6582-109">Eine Flusssteuerungsgrenze für den Instanzkontext wird einmal für jeden Kontext verfolgt.</span><span class="sxs-lookup"><span data-stu-id="d6582-109">Flow control limit on the instance context is traced once for each context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6582-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6582-110">See also</span></span>

- [<span data-ttu-id="d6582-111">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="d6582-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="d6582-112">Verwenden der Ablaufverfolgung zum Beheben von Anwendungsfehlern</span><span class="sxs-lookup"><span data-stu-id="d6582-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d6582-113">Verwaltung und Diagnose</span><span class="sxs-lookup"><span data-stu-id="d6582-113">Administration and Diagnostics</span></span>](../index.md)
