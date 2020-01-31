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
ms.openlocfilehash: 710dbe70b0a2498a3d521cdc813c4ead7ba6442e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866428"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="cb80e-102">ICorProfilerCallback::ExceptionSearchFilterEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="cb80e-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="cb80e-103">Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung mit dem Ausführen eines benutzerdefinierten Ausnahme Filters begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="cb80e-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb80e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb80e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb80e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="cb80e-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="cb80e-106">\[in] die ID der Funktion, die den Filter enthält.</span><span class="sxs-lookup"><span data-stu-id="cb80e-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb80e-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb80e-107">Requirements</span></span>  
 <span data-ttu-id="cb80e-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb80e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb80e-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb80e-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb80e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb80e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb80e-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb80e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb80e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb80e-112">See also</span></span>

- [<span data-ttu-id="cb80e-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb80e-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="cb80e-114">ExceptionSearchFilterLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="cb80e-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
