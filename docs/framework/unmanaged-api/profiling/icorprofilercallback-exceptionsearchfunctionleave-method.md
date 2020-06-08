---
title: ICorProfilerCallback::ExceptionSearchFunctionLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
ms.openlocfilehash: 11ce99fe650f68b80c380c740472e5e0ac8904db
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500181"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="35d30-102">ICorProfilerCallback::ExceptionSearchFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="35d30-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="35d30-103">Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung das Durchsuchen einer Funktion abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="35d30-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35d30-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="35d30-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="35d30-105">Requirements</span></span>  
 <span data-ttu-id="35d30-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d30-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d30-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35d30-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35d30-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35d30-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35d30-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d30-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d30-110">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="35d30-110">See also</span></span>

- [<span data-ttu-id="35d30-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35d30-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="35d30-112">ExceptionSearchFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="35d30-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
