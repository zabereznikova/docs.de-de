---
title: ICorProfilerCallback::ExceptionSearchFilterEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
ms.openlocfilehash: d58f2013e93eb1c7030d26ec60b0ab5ab08d0524
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699858"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="7031a-102">ICorProfilerCallback::ExceptionSearchFilterEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="7031a-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>

<span data-ttu-id="7031a-103">Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung mit dem Ausführen eines benutzerdefinierten Ausnahme Filters begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="7031a-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7031a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7031a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7031a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7031a-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="7031a-106">\[in] die ID der Funktion, die den Filter enthält.</span><span class="sxs-lookup"><span data-stu-id="7031a-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="7031a-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7031a-107">Requirements</span></span>  

 <span data-ttu-id="7031a-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7031a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7031a-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7031a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7031a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7031a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7031a-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7031a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7031a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7031a-112">See also</span></span>

- [<span data-ttu-id="7031a-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7031a-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7031a-114">ExceptionSearchFilterLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="7031a-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
