---
title: COR_PRF_SUSPEND_REASON-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SUSPEND_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SUSPEND_REASON
helpviewer_keywords: COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aef9688d3da047645d53f6fcf113153393780c8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="0986b-102">COR_PRF_SUSPEND_REASON-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0986b-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="0986b-103">Gibt den Grund, dass die Laufzeit angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="0986b-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0986b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0986b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0986b-105">Member</span><span class="sxs-lookup"><span data-stu-id="0986b-105">Members</span></span>  
  
|<span data-ttu-id="0986b-106">Member</span><span class="sxs-lookup"><span data-stu-id="0986b-106">Member</span></span>|<span data-ttu-id="0986b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0986b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="0986b-108">Die Laufzeit ist aus Unbekannter Ursache unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="0986b-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="0986b-109">Die Common Language Runtime wird angehalten, um eine Garbage Collection-Anforderung zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="0986b-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="0986b-110">Die Garbage Collection-bezogene Rückrufe treten zwischen den [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) und [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="0986b-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="0986b-111">Die Common Language Runtime wird angehalten, damit ein `AppDomain` heruntergefahren werden kann.</span><span class="sxs-lookup"><span data-stu-id="0986b-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="0986b-112">Während die Laufzeit angehalten ist, die Common Language Runtime bestimmen, welche Threads in werden die `AppDomain` also heruntergefahren wird, und richten sie abgebrochen wird, wenn sie fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="0986b-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="0986b-113">Es gibt keine `AppDomain`-spezifische Rückrufe während diese Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="0986b-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="0986b-114">Die Common Language Runtime wird angehalten, sodass Codepitching auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="0986b-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="0986b-115">Codepitching erfolgt nur, wenn der Just-in-Time (JIT)-Compiler aktiv ist und Codepitching aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0986b-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="0986b-116">Codepitchingrückrufe treten zwischen den `ICorProfilerCallback::RuntimeSuspendFinished` und `ICorProfilerCallback::RuntimeResumeStarted` Rückrufe.</span><span class="sxs-lookup"><span data-stu-id="0986b-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="0986b-117">**Hinweis:** der CLR-JIT ist nicht der Verkaufspräsentation Funktionen in .NET Framework, Version 2.0, damit dieser Wert nicht in 2.0 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0986b-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="0986b-118">Die Common Language Runtime wird angehalten, sodass er heruntergefahren werden kann.</span><span class="sxs-lookup"><span data-stu-id="0986b-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="0986b-119">Sie müssen alle Threads zum Abschließen des Vorgangs anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="0986b-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="0986b-120">Die Laufzeit wird für prozessinternes Debuggen angehalten.</span><span class="sxs-lookup"><span data-stu-id="0986b-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="0986b-121">Die Common Language Runtime wird angehalten, um für eine Garbagecollection vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="0986b-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="0986b-122">Die Common Language Runtime ist für die JIT-Neukompilierung angehalten.</span><span class="sxs-lookup"><span data-stu-id="0986b-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0986b-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0986b-123">Remarks</span></span>  
 <span data-ttu-id="0986b-124">Weiter ausgeführt wird, bis sie versuchen, die Laufzeit erneut eingeben, an welchem, die Punkt sie auch angehalten werden, bis die Laufzeit fortgesetzt wird, sind alle Common Language Runtime-Threads, die in nicht verwaltetem Code sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="0986b-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="0986b-125">Dies gilt auch für neue Threads, die die Common Language Runtime eingeben.</span><span class="sxs-lookup"><span data-stu-id="0986b-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="0986b-126">Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn der Code parallelisiert werden, oder aufgefordert, angehalten, wenn sie unterbrechbaren Code erreichen.</span><span class="sxs-lookup"><span data-stu-id="0986b-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0986b-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0986b-127">Requirements</span></span>  
 <span data-ttu-id="0986b-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0986b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0986b-129">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0986b-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0986b-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0986b-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0986b-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0986b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0986b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0986b-132">See Also</span></span>  
 [<span data-ttu-id="0986b-133">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="0986b-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
