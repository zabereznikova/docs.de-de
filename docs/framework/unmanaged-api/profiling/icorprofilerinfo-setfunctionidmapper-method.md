---
title: ICorProfilerInfo::SetFunctionIDMapper-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6cbbe85a99d0c78bd3d95ee654bdc13e376d017d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125223"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="de23e-102">ICorProfilerInfo::SetFunctionIDMapper-Methode</span><span class="sxs-lookup"><span data-stu-id="de23e-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="de23e-103">Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="de23e-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de23e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de23e-104">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de23e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de23e-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="de23e-106">[in] Ein Zeiger auf die [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) -Implementierung, die aufgerufen wird, um das Zuordnen der `FunctionID` -Werte alternativen Werten.</span><span class="sxs-lookup"><span data-stu-id="de23e-106">[in] A pointer to the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de23e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de23e-107">Remarks</span></span>  
 <span data-ttu-id="de23e-108">Die alternativen für die `FunctionID` Werte werden an die Einstiegs-/ausstiegsspunkt-Hooks der Funktion übergeben ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), und [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) dem angegebenen die [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="de23e-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="de23e-109">Die `FunctionIDMapper` kann nur einmal festgelegt werden, und es wird empfohlen, sie Sie in legen der [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="de23e-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de23e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de23e-110">Requirements</span></span>  
 <span data-ttu-id="de23e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de23e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de23e-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de23e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="de23e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de23e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de23e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de23e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de23e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de23e-115">See also</span></span>

- [<span data-ttu-id="de23e-116">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de23e-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
