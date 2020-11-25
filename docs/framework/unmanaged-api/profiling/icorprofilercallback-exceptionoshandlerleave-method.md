---
title: ICorProfilerCallback::ExceptionOSHandlerLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
ms.openlocfilehash: 37e3c9139a202e3cb31bd824d182389ae10b7389
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699923"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="db629-102">ICorProfilerCallback::ExceptionOSHandlerLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="db629-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>

<span data-ttu-id="db629-103">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="db629-103">Not implemented.</span></span> <span data-ttu-id="db629-104">Ein Profiler, der Informationen zu nicht verwalteten Ausnahmen benötigt, muss diese Informationen auf andere Weise abrufen.</span><span class="sxs-lookup"><span data-stu-id="db629-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db629-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="db629-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="db629-106">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="db629-106">Requirements</span></span>  

 <span data-ttu-id="db629-107">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db629-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db629-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db629-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db629-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db629-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db629-110">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db629-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db629-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db629-111">See also</span></span>

- [<span data-ttu-id="db629-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db629-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
