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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c49a9543c7bfeb9882144fba74b9c48cfba64890
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393388"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="1b484-102">ICorDebugFunction3::GetActiveReJitRequestILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="1b484-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="1b484-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="1b484-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1b484-104">Ruft einen Schnittstellenzeiger auf ein [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , der die IL aus einer aktiven ReJIT-Anfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="1b484-104">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b484-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b484-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b484-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b484-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="1b484-107">Ein Zeiger auf die IL einer aktiven ReJIT-Anfrage.</span><span class="sxs-lookup"><span data-stu-id="1b484-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b484-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b484-108">Remarks</span></span>  
 <span data-ttu-id="1b484-109">Wenn die Methode, die durch dieses `ICorDebugFunction3`-Objekt dargestellt wird, über eine aktive ReJIT-Anfrage verfügt, gibt `ppReJitedILCode` einen Zeiger auf deren IL aus.</span><span class="sxs-lookup"><span data-stu-id="1b484-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="1b484-110">Es ist keine aktive Anfrage, die häufig vorkommt, dann kann `ppReJitedILCode` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="1b484-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="1b484-111">Eine ReJIT-Anfrage wird aktiv, unmittelbar nach der Ausführung zurückgegeben werden, aus der [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) Methodenaufruf.</span><span class="sxs-lookup"><span data-stu-id="1b484-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="1b484-112">Möglicherweise liegt noch keine JIT-Kompilierung vor und Threads werden immer noch in der ursprünglichen Version des Codes ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b484-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="1b484-113">Eine ReJIT-Anfrage wird inaktiv, während der Profiler Aufruf an die [icorprofilerinfo4:: Requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="1b484-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="1b484-114">Selbst wenn die IL zurückgesetzt wurde, kann ein Thread immer noch im erneut JIT-kompilierten (ReJIT) Code ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1b484-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b484-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b484-115">Requirements</span></span>  
 <span data-ttu-id="1b484-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b484-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b484-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b484-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b484-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b484-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b484-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b484-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b484-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b484-120">See Also</span></span>  
 [<span data-ttu-id="1b484-121">ICorDebugFunction3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b484-121">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [<span data-ttu-id="1b484-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1b484-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1b484-123">ReJIT: Anleitung</span><span class="sxs-lookup"><span data-stu-id="1b484-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
