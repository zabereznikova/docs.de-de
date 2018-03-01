---
title: ICorProfilerCallback::JITFunctionPitched-Methode
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
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 48432911d7844e6519689961c985da37219179a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="4fb34-102">ICorProfilerCallback::JITFunctionPitched-Methode</span><span class="sxs-lookup"><span data-stu-id="4fb34-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="4fb34-103">Benachrichtigt den Profiler, die eine Funktion, die in-Time (JIT)-Kompilierung wurde aus dem Arbeitsspeicher entfernt.</span><span class="sxs-lookup"><span data-stu-id="4fb34-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fb34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fb34-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4fb34-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4fb34-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4fb34-106">[in] Die ID der Funktion, die entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="4fb34-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fb34-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fb34-107">Remarks</span></span>  
 <span data-ttu-id="4fb34-108">Wenn die entfernte Funktion aufgerufen wird, erhält der Profiler neue JIT-Kompilierung Ereignisse aus, wenn die Funktion neu kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4fb34-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="4fb34-109">JIT-Compiler der common Language Runtime (CLR) entfernen derzeit nicht Funktionen aus dem Arbeitsspeicher, damit dieser Rückruf zurzeit nicht verwendet wird und nicht vom Profiler empfangen.</span><span class="sxs-lookup"><span data-stu-id="4fb34-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="4fb34-110">Der Wert des `functionId` ist nicht gültig, bis die Funktion neu kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4fb34-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="4fb34-111">Wenn die Funktion neu kompiliert wird, die gleiche `functionId` Wert verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4fb34-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fb34-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4fb34-112">Requirements</span></span>  
 <span data-ttu-id="4fb34-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fb34-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fb34-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4fb34-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4fb34-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fb34-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fb34-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fb34-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb34-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fb34-117">See Also</span></span>  
 [<span data-ttu-id="4fb34-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fb34-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
