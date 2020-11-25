---
title: EClrOperation-Enumeration
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: c24e4557695d26666682ee385131abaab707a24d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720710"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="e90fb-102">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e90fb-102">EClrOperation Enumeration</span></span>

<span data-ttu-id="e90fb-103">Beschreibt den Satz von Vorgängen, für die ein Host Richtlinien Aktionen anwenden kann.</span><span class="sxs-lookup"><span data-stu-id="e90fb-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e90fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e90fb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="e90fb-105">Member</span><span class="sxs-lookup"><span data-stu-id="e90fb-105">Members</span></span>  
  
|<span data-ttu-id="e90fb-106">Member</span><span class="sxs-lookup"><span data-stu-id="e90fb-106">Member</span></span>|<span data-ttu-id="e90fb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e90fb-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="e90fb-108">Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn eine <xref:System.AppDomain> nicht ordnungsgemäß (grob) entladen wird.</span><span class="sxs-lookup"><span data-stu-id="e90fb-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="e90fb-109">Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein <xref:System.AppDomain> entladen wird.</span><span class="sxs-lookup"><span data-stu-id="e90fb-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="e90fb-110">Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn Finalizer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e90fb-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="e90fb-111">Der Host kann Richtlinien Aktionen angeben, die durchgeführt werden sollen, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e90fb-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="e90fb-112">Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein Thread abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="e90fb-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="e90fb-113">Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein unhöflicher Thread Abbruch in einem kritischen Code Bereich auftritt.</span><span class="sxs-lookup"><span data-stu-id="e90fb-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="e90fb-114">Der Host kann Richtlinien Aktionen angeben, die ausgeführt werden sollen, wenn ein grober Thread Abbruch in einem nicht kritischen Code Bereich auftritt.</span><span class="sxs-lookup"><span data-stu-id="e90fb-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e90fb-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e90fb-115">Remarks</span></span>  

 <span data-ttu-id="e90fb-116">Die Common Language Runtime (CLR)-Zuverlässigkeits Infrastruktur unterscheidet zwischen Abbrüchen und Ressourcen Zuordnungs Fehlern, die in kritischen Codebereichen auftreten, sowie in nicht kritischen Codebereichen.</span><span class="sxs-lookup"><span data-stu-id="e90fb-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="e90fb-117">Dieser Unterschied ist so konzipiert, dass Hosts verschiedene Richtlinien festlegen können, je nachdem, wo ein Fehler im Code auftritt.</span><span class="sxs-lookup"><span data-stu-id="e90fb-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="e90fb-118">Ein *kritischer Bereich von Code* ist ein beliebiger Speicherplatz, der von der CLR nicht garantiert werden kann, dass das Abbrechen einer Aufgabe oder das Fehlschlagen einer Anforderung für Ressourcen nur die aktuelle Aufgabe beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="e90fb-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="e90fb-119">Wenn eine Aufgabe z. b. eine Sperre aufrecht erhält und ein HRESULT empfängt, das einen Fehler beim Erstellen einer Speicher Belegungs Anforderung angibt, genügt es nicht, diese Aufgabe abzubrechen, um die Stabilität des zu gewährleisten <xref:System.AppDomain> , da das <xref:System.AppDomain> möglicherweise andere Tasks enthält, die auf die gleiche Sperre warten.</span><span class="sxs-lookup"><span data-stu-id="e90fb-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="e90fb-120">Das Abbrechen der aktuellen Aufgabe kann dazu führen, dass diese anderen Tasks nicht mehr reagieren.</span><span class="sxs-lookup"><span data-stu-id="e90fb-120">To abandon the current task might cause those other tasks to stop responding.</span></span> <span data-ttu-id="e90fb-121">In einem solchen Fall benötigt der Host die Möglichkeit, die gesamte zu entladen, <xref:System.AppDomain> anstatt potenzielle Instabilität zu gefährden.</span><span class="sxs-lookup"><span data-stu-id="e90fb-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="e90fb-122">Ein *nicht kritischer Code Bereich* ist andererseits eine Region, in der die CLR gewährleisten kann, dass ein Abbruch oder ein Fehler nur die Aufgabe beeinträchtigt, bei der der Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="e90fb-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="e90fb-123">Die CLR unterscheidet auch zwischen ordnungsgemäßen und nicht ordnungsgemäßen (unhöflichen) Abbrüchen.</span><span class="sxs-lookup"><span data-stu-id="e90fb-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="e90fb-124">Im Allgemeinen macht ein normaler oder ordnungsgemäßer Abbruch jeden Aufwand, um Routinen und Finalizer für die Ausnahmebehandlung auszuführen, bevor eine Aufgabe abgebrochen wird, während ein unhöflicher Abbruch keine Garantie dafür gibt.</span><span class="sxs-lookup"><span data-stu-id="e90fb-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e90fb-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e90fb-125">Requirements</span></span>  

 <span data-ttu-id="e90fb-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e90fb-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e90fb-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e90fb-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e90fb-128">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e90fb-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e90fb-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e90fb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90fb-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e90fb-130">See also</span></span>

- [<span data-ttu-id="e90fb-131">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e90fb-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="e90fb-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e90fb-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="e90fb-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e90fb-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="e90fb-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e90fb-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="e90fb-135">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e90fb-135">Hosting Enumerations</span></span>](hosting-enumerations.md)
