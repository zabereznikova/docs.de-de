---
title: COR_PRF_SUSPEND_REASON-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b40533553ccd7a3339a8a3ee0c8b47879efd38ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742460"
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="badcc-102">COR_PRF_SUSPEND_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="badcc-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="badcc-103">Gibt den Grund, dass die Laufzeit angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="badcc-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="badcc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="badcc-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="badcc-105">Member</span><span class="sxs-lookup"><span data-stu-id="badcc-105">Members</span></span>  
  
|<span data-ttu-id="badcc-106">Member</span><span class="sxs-lookup"><span data-stu-id="badcc-106">Member</span></span>|<span data-ttu-id="badcc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="badcc-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="badcc-108">Die Laufzeit ist aus Unbekannter Ursache unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="badcc-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="badcc-109">Die Laufzeit wird angehalten, um eine Garbage Collection-Anforderung zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="badcc-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="badcc-110">Die Rückrufe für die Garbage Collection-bezogene treten zwischen den [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) und [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="badcc-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="badcc-111">Die Laufzeit wird angehalten, damit ein `AppDomain` heruntergefahren werden kann.</span><span class="sxs-lookup"><span data-stu-id="badcc-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="badcc-112">Während die Laufzeit angehalten ist, die Laufzeit wird festzulegen, welche Threads im werden die `AppDomain` , heruntergefahren wird, und legen Sie sie Abbrechen, wenn sie fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="badcc-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="badcc-113">Es gibt keine `AppDomain`-spezifische Rückrufe während dieses Aussetzens.</span><span class="sxs-lookup"><span data-stu-id="badcc-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="badcc-114">Die Laufzeit wird unterbrochen, sodass Codepitching auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="badcc-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="badcc-115">Codepitching erfolgt nur, wenn der just-in-Time-Compiler (JIT) aktiv ist und Codepitching aktiviert.</span><span class="sxs-lookup"><span data-stu-id="badcc-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="badcc-116">Codepitchingrückrufe treten zwischen den `ICorProfilerCallback::RuntimeSuspendFinished` und `ICorProfilerCallback::RuntimeResumeStarted` Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="badcc-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="badcc-117">**Hinweis**:  Die CLR-JIT ist nicht Funktionen in .NET Framework, Version 2.0, präsentieren, damit dieser Wert nicht in 2.0 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="badcc-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="badcc-118">Die Laufzeit wird unterbrochen, sodass er heruntergefahren werden kann.</span><span class="sxs-lookup"><span data-stu-id="badcc-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="badcc-119">Sie müssen alle Threads zum Abschließen des Vorgangs anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="badcc-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="badcc-120">Die Laufzeit wird für das prozessinterne Debuggen angehalten.</span><span class="sxs-lookup"><span data-stu-id="badcc-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="badcc-121">Die Laufzeit wird angehalten, um für eine Garbagecollection vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="badcc-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="badcc-122">Die Laufzeit wird für die JIT-Neukompilierung unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="badcc-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="badcc-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="badcc-123">Remarks</span></span>  
 <span data-ttu-id="badcc-124">Alle Threads mit Common Language Runtime, die in nicht verwaltetem Code dürfen weiterhin ausgeführt, bis sie versuchen, die Runtime erneut eingeben, an welcher, die Stelle sie auch angehalten werden, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="badcc-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="badcc-125">Dies gilt auch für neue Threads, die die Laufzeit eingeben.</span><span class="sxs-lookup"><span data-stu-id="badcc-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="badcc-126">Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn sie in der unterbrechbare Code sind, oder aufgefordert, anhalten, wenn sie unterbrechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="badcc-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="badcc-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="badcc-127">Requirements</span></span>  
 <span data-ttu-id="badcc-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="badcc-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="badcc-129">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="badcc-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="badcc-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="badcc-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="badcc-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="badcc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="badcc-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="badcc-132">See also</span></span>
- [<span data-ttu-id="badcc-133">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="badcc-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
