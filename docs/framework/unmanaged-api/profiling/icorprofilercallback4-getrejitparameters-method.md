---
title: ICorProfilerCallback4::GetReJITParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: d81d7275d197de1dfc99b135377459f509c2651f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439437"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="9f2e9-102">ICorProfilerCallback4::GetReJITParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="9f2e9-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="9f2e9-103">Ermöglicht dem Codeprofiler das Festlegen von Flags für die Alternative Codegenerierung für einen neuen neu kompilierten Methoden Text.</span><span class="sxs-lookup"><span data-stu-id="9f2e9-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f2e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f2e9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f2e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f2e9-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="9f2e9-106">in Das Modul, das die Methode enthält, für die die CLR JIT-neukompilierungs Parameter benötigt.</span><span class="sxs-lookup"><span data-stu-id="9f2e9-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="9f2e9-107">in Der `MethodDef` der Methode, für die die CLR JIT-neukompilierungs Parameter benötigt.</span><span class="sxs-lookup"><span data-stu-id="9f2e9-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="9f2e9-108">in Ein Zeiger auf eine [icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) -Schnittstelle, die der Profiler verwenden kann, um JIT-neukompilierungs Informationen für die neu kompilierte Methode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9f2e9-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f2e9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f2e9-109">Remarks</span></span>  
 <span data-ttu-id="9f2e9-110">Die CLR gibt einen `GetReJITParameters` Rückruf aus, sodass der Profiler die Parameter zum erneuten Kompilieren einer bestimmten Methode angeben kann.</span><span class="sxs-lookup"><span data-stu-id="9f2e9-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="9f2e9-111">Der `GetReJITParameters` Rückruf wird nur einmal pro Funktion ausgegeben. die Parameter, die vom Profiler bereitgestellt werden, gelten für alle Instanzen dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="9f2e9-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f2e9-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9f2e9-112">Requirements</span></span>  
 <span data-ttu-id="9f2e9-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f2e9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f2e9-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9f2e9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9f2e9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f2e9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f2e9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f2e9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2e9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f2e9-117">See also</span></span>

- [<span data-ttu-id="9f2e9-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f2e9-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="9f2e9-119">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f2e9-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="9f2e9-120">JITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="9f2e9-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="9f2e9-121">ReJITCompilationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="9f2e9-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
