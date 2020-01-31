---
title: ICorProfilerCallback::AppDomainCreationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
ms.openlocfilehash: 49c3ab4901537805a1ae1be79097c55cc331d29d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866714"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="0f408-102">ICorProfilerCallback::AppDomainCreationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="0f408-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="0f408-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0f408-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f408-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f408-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f408-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0f408-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="0f408-106">\[in] identifiziert die Domäne, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0f408-106">\[in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0f408-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f408-107">Remarks</span></span>  
 <span data-ttu-id="0f408-108">Die ID ist für keine Informationsanforderung gültig, bis die [ICorProfilerCallback:: appdomaincreationbeendete](icorprofilercallback-appdomaincreationfinished-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0f408-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f408-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f408-109">Requirements</span></span>  
 <span data-ttu-id="0f408-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f408-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f408-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f408-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f408-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f408-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f408-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f408-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f408-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f408-114">See also</span></span>

- [<span data-ttu-id="0f408-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f408-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
