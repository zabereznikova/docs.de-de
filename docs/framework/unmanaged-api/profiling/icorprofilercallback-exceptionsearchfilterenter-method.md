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
ms.openlocfilehash: 96ca2b926217ced6c88f8890f0facc7346fe10c7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790140"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="4dea1-102">ICorProfilerCallback::ExceptionSearchFilterEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="4dea1-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="4dea1-103">Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung mit dem Ausführen eines benutzerdefinierten Ausnahme Filters begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="4dea1-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dea1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dea1-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dea1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4dea1-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="4dea1-106">\[in] die ID der Funktion, die den Filter enthält.</span><span class="sxs-lookup"><span data-stu-id="4dea1-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="4dea1-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4dea1-107">Requirements</span></span>  
 <span data-ttu-id="4dea1-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dea1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dea1-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4dea1-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4dea1-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dea1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dea1-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dea1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dea1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dea1-112">See also</span></span>

- [<span data-ttu-id="4dea1-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dea1-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4dea1-114">ExceptionSearchFilterLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="4dea1-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
