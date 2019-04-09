---
title: ICorProfilerCallback::JITFunctionPitched-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8aa46e869d50fc7aa65c1d4244ad4ff71657bad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186393"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="70cc4-102">ICorProfilerCallback::JITFunctionPitched-Methode</span><span class="sxs-lookup"><span data-stu-id="70cc4-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="70cc4-103">Benachrichtigt den Profiler, die eine Funktion, die just-in-Time (JIT)-kompiliert wurde aus dem Arbeitsspeicher entfernt.</span><span class="sxs-lookup"><span data-stu-id="70cc4-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70cc4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70cc4-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70cc4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="70cc4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="70cc4-106">[in] Die ID der Funktion, die entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="70cc4-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70cc4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70cc4-107">Remarks</span></span>  
 <span data-ttu-id="70cc4-108">Wenn die entfernte-Funktion aufgerufen wird, erhält der Profiler den neuen JIT-Kompilierung Ereignisse aus, wenn die Funktion neu kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="70cc4-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="70cc4-109">Derzeit werden JIT-Compiler der common Language Runtime (CLR) nicht entfernt Funktionen aus dem Arbeitsspeicher, damit dieser Rückruf derzeit nicht verwendet wird und wird nicht vom Profiler empfangen.</span><span class="sxs-lookup"><span data-stu-id="70cc4-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="70cc4-110">Der Wert des `functionId` ist nicht gültig, bis die Funktion neu kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="70cc4-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="70cc4-111">Wenn die Funktion neu kompiliert wird, gleich `functionId` Wert verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70cc4-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70cc4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70cc4-112">Requirements</span></span>  
 <span data-ttu-id="70cc4-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70cc4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70cc4-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="70cc4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="70cc4-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70cc4-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="70cc4-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="70cc4-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="70cc4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70cc4-117">See also</span></span>

- [<span data-ttu-id="70cc4-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70cc4-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
