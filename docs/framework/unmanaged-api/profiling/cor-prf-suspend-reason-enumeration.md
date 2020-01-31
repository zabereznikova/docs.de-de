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
ms.openlocfilehash: 1036ecbdb735b95c0ad6897c1545e3bd8cb6c3a9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867073"
---
# <a name="cor_prf_suspend_reason-enumeration"></a><span data-ttu-id="59744-102">COR_PRF_SUSPEND_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="59744-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="59744-103">Gibt den Grund an, warum die Laufzeit angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="59744-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59744-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59744-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="59744-105">Member</span><span class="sxs-lookup"><span data-stu-id="59744-105">Members</span></span>  
  
|<span data-ttu-id="59744-106">Member</span><span class="sxs-lookup"><span data-stu-id="59744-106">Member</span></span>|<span data-ttu-id="59744-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59744-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="59744-108">Die Laufzeit wird aus einem nicht angegebenen Grund angehalten.</span><span class="sxs-lookup"><span data-stu-id="59744-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="59744-109">Die Laufzeit wird angehalten, um eine Garbage Collection Anforderung zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="59744-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="59744-110">Die Garbage Collection bezogenen Rückrufe treten zwischen den Rückrufe [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendfinished-method.md) und [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) auf.</span><span class="sxs-lookup"><span data-stu-id="59744-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="59744-111">Die Laufzeit wird angehalten, sodass ein `AppDomain` heruntergefahren werden kann.</span><span class="sxs-lookup"><span data-stu-id="59744-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="59744-112">Während die Laufzeit angehalten wird, bestimmt die Common Language Runtime, welche Threads sich in der `AppDomain` befinden, die heruntergefahren wird, und legt Sie fest, wenn Sie fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="59744-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="59744-113">Während dieser Unterbrechung sind keine `AppDomain`-spezifischen Rückrufe vorhanden.</span><span class="sxs-lookup"><span data-stu-id="59744-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="59744-114">Die Laufzeit wird angehalten, sodass Code-Codepitching erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="59744-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="59744-115">Code-Codepitching verläuft nur, wenn der JIT-Compiler (Just-in-Time) aktiv ist und die Code-Codepitching aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="59744-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="59744-116">Code-Codepitching-Rückrufe treten zwischen den `ICorProfilerCallback::RuntimeSuspendFinished` und `ICorProfilerCallback::RuntimeResumeStarted` Rückrufen auf.</span><span class="sxs-lookup"><span data-stu-id="59744-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="59744-117">**Hinweis:**  Die CLR-JIT stellt keine Funktionen in der .NET Framework Version 2,0 dar, daher wird dieser Wert nicht in 2,0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="59744-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="59744-118">Die Laufzeit wird angehalten, sodass Sie heruntergefahren werden kann.</span><span class="sxs-lookup"><span data-stu-id="59744-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="59744-119">Alle Threads müssen angehalten werden, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="59744-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="59744-120">Die Laufzeit wird für das Prozess interne Debuggen angehalten.</span><span class="sxs-lookup"><span data-stu-id="59744-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="59744-121">Die Laufzeit wird angehalten, um eine Garbage Collection vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="59744-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="59744-122">Die Laufzeit wird bei der JIT-Neukompilierung angehalten.</span><span class="sxs-lookup"><span data-stu-id="59744-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59744-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59744-123">Remarks</span></span>  
 <span data-ttu-id="59744-124">Alle Laufzeitthreads in nicht verwaltetem Code können weiter ausgeführt werden, bis Sie versuchen, die Laufzeit erneut einzugeben. an diesem Punkt werden Sie auch angehalten, bis die Laufzeit fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="59744-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="59744-125">Dies gilt auch für neue Threads, die zur Laufzeit gelangen.</span><span class="sxs-lookup"><span data-stu-id="59744-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="59744-126">Alle Threads innerhalb der Laufzeit werden entweder sofort angehalten, wenn Sie sich in unter Brechungs barem Code befinden oder angehalten werden, wenn Sie unter brechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="59744-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59744-127">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59744-127">Requirements</span></span>  
 <span data-ttu-id="59744-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59744-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59744-129">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59744-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59744-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59744-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59744-131">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59744-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59744-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59744-132">See also</span></span>

- [<span data-ttu-id="59744-133">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="59744-133">Profiling Enumerations</span></span>](profiling-enumerations.md)
