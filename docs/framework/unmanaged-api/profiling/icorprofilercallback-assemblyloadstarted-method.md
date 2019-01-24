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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: deb8475ab338c6ce733f1700e509dff982bd697f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611175"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="bd5c5-102">ICorProfilerCallback::AssemblyLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="bd5c5-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="bd5c5-103">Benachrichtigt den Profiler an, dass eine Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="bd5c5-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd5c5-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd5c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd5c5-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="bd5c5-106">[in] Identifiziert die Assembly, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="bd5c5-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd5c5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd5c5-107">Remarks</span></span>  
 <span data-ttu-id="bd5c5-108">Der Wert des `assemblyId` gilt nicht für eine Anforderung von Informationen bis der [ICorProfilerCallback:: AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bd5c5-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd5c5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd5c5-109">Requirements</span></span>  
 <span data-ttu-id="bd5c5-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd5c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd5c5-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd5c5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd5c5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd5c5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd5c5-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd5c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5c5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd5c5-114">See also</span></span>
- [<span data-ttu-id="bd5c5-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd5c5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
