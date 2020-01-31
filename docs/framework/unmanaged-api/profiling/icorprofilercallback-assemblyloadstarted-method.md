---
title: ICorProfilerCallback::AssemblyLoadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
ms.openlocfilehash: 9899ea8afc739207ad0b70e9720e90e5c7f09fcf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790193"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="d77a9-102">ICorProfilerCallback::AssemblyLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="d77a9-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="d77a9-103">Benachrichtigt den Profiler, dass eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="d77a9-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d77a9-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d77a9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d77a9-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="d77a9-106">\[in] identifiziert die Assembly, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="d77a9-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="d77a9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d77a9-107">Remarks</span></span>  
 <span data-ttu-id="d77a9-108">Der Wert `assemblyId` ist für eine Informationsanforderung erst gültig, wenn die [ICorProfilerCallback:: assemblyloadabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d77a9-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d77a9-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d77a9-109">Requirements</span></span>  
 <span data-ttu-id="d77a9-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d77a9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d77a9-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d77a9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d77a9-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d77a9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d77a9-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d77a9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d77a9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d77a9-114">See also</span></span>

- [<span data-ttu-id="d77a9-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d77a9-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
