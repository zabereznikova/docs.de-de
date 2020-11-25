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
ms.openlocfilehash: c2fbc0ae8cdeb79b65cbad9a055a8051acf67e50
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700417"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="57a21-102">ICorProfilerCallback::AssemblyLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="57a21-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>

<span data-ttu-id="57a21-103">Benachrichtigt den Profiler, dass eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="57a21-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57a21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57a21-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57a21-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="57a21-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="57a21-106">\[in] identifiziert die Assembly, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="57a21-106">\[in] Identifies the assembly that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="57a21-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57a21-107">Remarks</span></span>  

 <span data-ttu-id="57a21-108">Der Wert von `assemblyId` ist für eine Informationsanforderung erst gültig, wenn die [ICorProfilerCallback:: assemblyloadfertige](icorprofilercallback-assemblyloadfinished-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="57a21-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57a21-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="57a21-109">Requirements</span></span>  

 <span data-ttu-id="57a21-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57a21-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57a21-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57a21-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57a21-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57a21-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57a21-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57a21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a21-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57a21-114">See also</span></span>

- [<span data-ttu-id="57a21-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57a21-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
