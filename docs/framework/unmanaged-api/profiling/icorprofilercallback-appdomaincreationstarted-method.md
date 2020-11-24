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
ms.openlocfilehash: 901546c80c3bee32afddfa8e8cffbd2b679bc43b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685391"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="0735d-102">ICorProfilerCallback::AppDomainCreationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="0735d-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>

<span data-ttu-id="0735d-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0735d-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0735d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0735d-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0735d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0735d-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="0735d-106">\[in] identifiziert die Domäne, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0735d-106">\[in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0735d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0735d-107">Remarks</span></span>  

 <span data-ttu-id="0735d-108">Die ID ist für keine Informationsanforderung gültig, bis die [ICorProfilerCallback:: appdomaincreationbeendete](icorprofilercallback-appdomaincreationfinished-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0735d-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0735d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0735d-109">Requirements</span></span>  

 <span data-ttu-id="0735d-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0735d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0735d-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0735d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0735d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0735d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0735d-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0735d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0735d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0735d-114">See also</span></span>

- [<span data-ttu-id="0735d-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0735d-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
