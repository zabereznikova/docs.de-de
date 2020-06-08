---
title: ICorDebugFunction3::GetActiveReJitRequestILCode-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: db9ce146da1d6fee8db32a0be43903eaa61e52de
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501754"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="a10ff-102">ICorDebugFunction3::GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="a10ff-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="a10ff-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="a10ff-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a10ff-104">Ruft einen Schnittstellen Zeiger auf einen [icordebugilcode](icordebugilcode-interface.md) ab, der die Il aus einer aktiven ReJIT-Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="a10ff-104">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a10ff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a10ff-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a10ff-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a10ff-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="a10ff-107">Ein Zeiger auf die IL einer aktiven ReJIT-Anfrage.</span><span class="sxs-lookup"><span data-stu-id="a10ff-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a10ff-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a10ff-108">Remarks</span></span>  
 <span data-ttu-id="a10ff-109">Wenn die Methode, die durch dieses `ICorDebugFunction3`-Objekt dargestellt wird, über eine aktive ReJIT-Anfrage verfügt, gibt `ppReJitedILCode` einen Zeiger auf deren IL aus.</span><span class="sxs-lookup"><span data-stu-id="a10ff-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="a10ff-110">Wenn keine aktive Anforderung vorhanden ist, was häufig der Fall ist, `ppReJitedILCode` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="a10ff-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="a10ff-111">Eine ReJIT-Anforderung wird unmittelbar nach der Ausführung des [ICorProfilerCallback4:: getrejitparameters](../profiling/icorprofilercallback4-getrejitparameters-method.md) -Methoden Aufrufes aktiv.</span><span class="sxs-lookup"><span data-stu-id="a10ff-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="a10ff-112">Möglicherweise liegt noch keine JIT-Kompilierung vor und Threads werden immer noch in der ursprünglichen Version des Codes ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a10ff-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="a10ff-113">Eine ReJIT-Anforderung wird beim Aufrufen der [ICorProfilerInfo4:: requestrevert](../profiling/icorprofilerinfo4-requestrevert-method.md) -Methode des Profilers inaktiv.</span><span class="sxs-lookup"><span data-stu-id="a10ff-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="a10ff-114">Selbst wenn die IL zurückgesetzt wurde, kann ein Thread immer noch im erneut JIT-kompilierten (ReJIT) Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a10ff-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a10ff-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a10ff-115">Requirements</span></span>  
 <span data-ttu-id="a10ff-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a10ff-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a10ff-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a10ff-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a10ff-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a10ff-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a10ff-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a10ff-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a10ff-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a10ff-120">See also</span></span>

- [<span data-ttu-id="a10ff-121">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a10ff-121">ICorDebugFunction3 Interface</span></span>](icordebugfunction3-interface.md)
- [<span data-ttu-id="a10ff-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a10ff-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a10ff-123">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="a10ff-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
