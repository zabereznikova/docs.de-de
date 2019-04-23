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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d5f24d7415ff7ecceba6b0a5fbd3098d70dcd0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190352"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="9b5be-102">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9b5be-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="9b5be-103">Beschreibt die Vorgänge, die für die ein Host Richtlinienaktionen anwenden kann.</span><span class="sxs-lookup"><span data-stu-id="9b5be-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b5be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b5be-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="9b5be-105">Member</span><span class="sxs-lookup"><span data-stu-id="9b5be-105">Members</span></span>  
  
|<span data-ttu-id="9b5be-106">Member</span><span class="sxs-lookup"><span data-stu-id="9b5be-106">Member</span></span>|<span data-ttu-id="9b5be-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b5be-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="9b5be-108">Der Host kann Aktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> Weise eine nicht ordnungsgemäß (grobe) entladen wird.</span><span class="sxs-lookup"><span data-stu-id="9b5be-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="9b5be-109">Der Host kann Aktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> entladen wird.</span><span class="sxs-lookup"><span data-stu-id="9b5be-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="9b5be-110">Der Host kann die Richtlinienaktionen ausgeführt werden, wenn der Finalizer ausgeführt angeben.</span><span class="sxs-lookup"><span data-stu-id="9b5be-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="9b5be-111">Der Host kann angeben, Richtlinienaktionen ausgeführt werden, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b5be-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="9b5be-112">Der Host kann die Richtlinienaktionen ausgeführt werden, wenn ein Thread abgebrochen angeben.</span><span class="sxs-lookup"><span data-stu-id="9b5be-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="9b5be-113">Der Host kann die Richtlinienaktionen ausgeführt werden, tritt ein grobe Threadabbruch in einem kritischen Bereich des Codes angeben.</span><span class="sxs-lookup"><span data-stu-id="9b5be-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="9b5be-114">Der Host kann die Richtlinienaktionen durchgeführt werden, tritt ein grobe Threadabbruch in einen nicht-kritische Codebereich angeben.</span><span class="sxs-lookup"><span data-stu-id="9b5be-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b5be-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b5be-115">Remarks</span></span>  
 <span data-ttu-id="9b5be-116">Die common Language Runtime (CLR) zuverlässigkeitsinfrastruktur unterscheidet zwischen Abbrüche und Ressource Fehler bei der Zuordnung, die auftreten, die im kritischen Bereich des Codes und diejenigen, die in nicht-kritische Bereiche des Codes auftreten.</span><span class="sxs-lookup"><span data-stu-id="9b5be-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="9b5be-117">Diese Unterscheidung soll es ermöglicht Hosts, die verschiedene Richtlinien, je nachdem, in denen eines im Code Fehlers festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9b5be-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="9b5be-118">Ein *des kritischen Codebereichs* ist eine beliebige Stelle, in denen die CLR kann nicht garantieren, diese eine Aufgabe oder Fehler beim Abschluss einer Anforderung für Ressourcen nur den aktuellen Task auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9b5be-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="9b5be-119">Z. B. wenn ein Task eine Sperre wird und empfängt ein HRESULT, das Fehler beim Erstellen einer speicherbelegungsanforderung weist darauf hin, es ist nicht ausreichend, einfach, um diese Aufgabe aus, um sicherzustellen, dass die Stabilität der Abbruch der <xref:System.AppDomain>, da die <xref:System.AppDomain> enthält möglicherweise andere Aufgaben, die die gleiche Sperre warten.</span><span class="sxs-lookup"><span data-stu-id="9b5be-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="9b5be-120">Verwerfen der aktuellen Aufgabe kann dazu führen, dass die andere Aufgaben nicht mehr reagiert (oder hängen) auf unbestimmte Zeit.</span><span class="sxs-lookup"><span data-stu-id="9b5be-120">To abandon the current task might cause those other tasks to stop responding (or hang) indefinitely.</span></span> <span data-ttu-id="9b5be-121">In diesem Fall benötigt der Host die Möglichkeit, den gesamten entladen <xref:System.AppDomain> statt Risiko potenzieller Systeminstabilität zur Folge.</span><span class="sxs-lookup"><span data-stu-id="9b5be-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="9b5be-122">Ein *unkritische Codebereich*, auf der anderen Seite ist eine Region, in denen die CLR garantieren kann, dass ein Abbruch oder Fehler auf dem der Fehler tritt nur auf die Aufgabe beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="9b5be-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="9b5be-123">Die CLR unterscheidet sich auch zwischen ordnungsgemäßen und nicht ordnungsgemäß (grobe) abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="9b5be-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="9b5be-124">Im Allgemeinen wird einem normalen oder ordnungsgemäßen Abbruch höchste anstrengungen, um die Behandlung von Ausnahmen und Finalizer ausgeführt, bevor eine Aufgabe, Ausnahmebehandlungsroutinen solche garantiert wird.</span><span class="sxs-lookup"><span data-stu-id="9b5be-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b5be-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b5be-125">Requirements</span></span>  
 <span data-ttu-id="9b5be-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b5be-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b5be-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9b5be-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b5be-128">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b5be-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b5be-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b5be-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5be-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b5be-130">See also</span></span>

- [<span data-ttu-id="9b5be-131">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9b5be-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="9b5be-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9b5be-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="9b5be-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b5be-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="9b5be-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b5be-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="9b5be-135">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9b5be-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
