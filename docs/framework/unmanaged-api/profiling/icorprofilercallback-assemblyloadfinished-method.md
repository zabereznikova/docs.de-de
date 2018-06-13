---
title: ICorProfilerCallback::AssemblyLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7f000b6e944be7bd2e38f97e40176952cb19605
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450631"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="bd0df-102">ICorProfilerCallback::AssemblyLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="bd0df-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="bd0df-103">Benachrichtigt den Profiler, dass eine Assembly geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd0df-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd0df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd0df-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd0df-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd0df-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="bd0df-106">[in] Identifiziert die Assembly, die geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd0df-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bd0df-107">[in] Ein HRESULT, das angibt, ob die Assembly vollständig erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="bd0df-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd0df-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd0df-108">Remarks</span></span>  
 <span data-ttu-id="bd0df-109">Der Wert der `assemblyId` gilt nicht für eine Anforderung Informationen, bis die `AssemblyLoadFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bd0df-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="bd0df-110">Einige Teile der beim Laden der Assembly möglicherweise weiterhin nach dem `AssemblyLoadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="bd0df-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="bd0df-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="bd0df-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bd0df-112">Allerdings ein Erfolgs-HRESULT in `hrStatus` bedeutet nur, dass der erste Teil, das Laden der Assembly erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bd0df-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd0df-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd0df-113">Requirements</span></span>  
 <span data-ttu-id="bd0df-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd0df-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd0df-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd0df-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd0df-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd0df-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd0df-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd0df-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd0df-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd0df-118">See Also</span></span>  
 [<span data-ttu-id="bd0df-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd0df-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
