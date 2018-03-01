---
title: EClrOperation-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 343ff04dba1a02660734beb726f9b895370a10af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="9a5c0-102">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9a5c0-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="9a5c0-103">Beschreibt den Satz von Vorgängen, die für die Richtlinienaktionen ein Host angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a5c0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9a5c0-105">Member</span><span class="sxs-lookup"><span data-stu-id="9a5c0-105">Members</span></span>  
  
|<span data-ttu-id="9a5c0-106">Member</span><span class="sxs-lookup"><span data-stu-id="9a5c0-106">Member</span></span>|<span data-ttu-id="9a5c0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a5c0-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="9a5c0-108">Der Host kann die Richtlinienaktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> nicht ordnungsgemäße (grobe) Weise entladen wird.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="9a5c0-109">Der Host kann die Richtlinienaktionen durchgeführt werden sollen angeben einer <xref:System.AppDomain> wird entladen.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="9a5c0-110">Der Host kann die Richtlinienaktionen, die ausgeführt werden, wenn Finalizer angeben.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="9a5c0-111">Der Host kann angeben, Richtlinienaktionen, die ausgeführt werden, wenn der Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="9a5c0-112">Der Host kann die Richtlinienaktionen, die ausgeführt werden, nach dem Abbrechen eines Threads angeben.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="9a5c0-113">Der Host kann die Richtlinienaktionen, die ausgeführt werden, tritt eine grobe Threadabbruchs in einem kritischen Codebereich angeben.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="9a5c0-114">Der Host kann die Richtlinienaktionen durchgeführt werden, tritt eine grobe Threadabbruchs in einem unkritische Codebereich angeben.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a5c0-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a5c0-115">Remarks</span></span>  
 <span data-ttu-id="9a5c0-116">Die common Language Runtime (CLR) Zuverlässigkeit Infrastruktur unterscheidet zwischen abgebrochen und Ressource belegungsfehler angezeigt, die in kritischen Bereiche des Codes und those, die occur an in unkritische Bereiche des Codes auftreten.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="9a5c0-117">Diese Unterscheidung dient zum Zulassen von Hosts, die verschiedene Richtlinien, je nachdem, wo eines im Code Fehlers festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="9a5c0-118">Ein *kritischen Codebereich* ist eine Stelle, wo die CLR kann nicht garantieren, eine Aufgabe oder ein auf eine Anforderung nicht abschließen für Ressourcen nur auf den aktuellen Task auswirkt.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="9a5c0-119">Beispielsweise, wenn eine Aufgabe ist eine Sperre aufrechterhält, und ein HRESULT, das erhält bei einer speicherbelegungsanforderung Fehler weist darauf hin, ist es nicht ausreichend, einfach, um diese Aufgabe aus, um sicherzustellen, dass die Stabilität der Abbruch der <xref:System.AppDomain>, da die <xref:System.AppDomain> enthält möglicherweise andere Aufgaben, die die gleiche Sperre warten.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="9a5c0-120">Für das Abbrechen des aktuellen Aufgabe kann dazu führen, dass die andere Tasks reagiert (oder bleibt hängen) unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-120">To abandon the current task might cause those other tasks to stop responding (or hang) indefinitely.</span></span> <span data-ttu-id="9a5c0-121">In diesem Fall benötigt der Host die Möglichkeit, den gesamten entladen <xref:System.AppDomain> anstatt potenzielle Instabilität Risiko.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="9a5c0-122">Ein *unkritische Codebereich*, eine Region, in denen die CLR garantieren kann, dass ein Abbruch oder Fehler nur auf den Task auswirkt auf dem der Fehler tritt auf, auf der anderen Seite ist.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="9a5c0-123">Die CLR unterscheidet sich auch zwischen ordnungsgemäßes und nicht ordnungsgemäß (grobe) abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="9a5c0-124">Im Allgemeinen wird einem normalen oder ordnungsgemäßen Abbruch bemüht, Ausnahmebehandlung und Finalizer vor dem Abbrechen einer Aufgabe trotz aller bemühungen Ausnahmebehandlungsroutinen solche Garantien ausführen.</span><span class="sxs-lookup"><span data-stu-id="9a5c0-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a5c0-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a5c0-125">Requirements</span></span>  
 <span data-ttu-id="9a5c0-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a5c0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a5c0-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a5c0-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a5c0-128">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="9a5c0-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a5c0-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a5c0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5c0-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a5c0-130">See Also</span></span>  
 [<span data-ttu-id="9a5c0-131">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9a5c0-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="9a5c0-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9a5c0-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="9a5c0-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a5c0-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="9a5c0-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a5c0-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="9a5c0-135">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9a5c0-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
