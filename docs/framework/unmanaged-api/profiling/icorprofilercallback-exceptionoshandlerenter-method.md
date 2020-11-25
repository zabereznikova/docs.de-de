---
title: ICorProfilerCallback::ExceptionOSHandlerEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: 273c3cefa2e67a7d8c429982b4da4126168b2830
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699962"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="595bd-102">ICorProfilerCallback::ExceptionOSHandlerEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="595bd-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>

<span data-ttu-id="595bd-103">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="595bd-103">Not implemented.</span></span> <span data-ttu-id="595bd-104">Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.</span><span class="sxs-lookup"><span data-stu-id="595bd-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="595bd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="595bd-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="595bd-106">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="595bd-106">Requirements</span></span>  

 <span data-ttu-id="595bd-107">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="595bd-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="595bd-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="595bd-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="595bd-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="595bd-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="595bd-110">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="595bd-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595bd-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="595bd-111">See also</span></span>

- [<span data-ttu-id="595bd-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="595bd-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
