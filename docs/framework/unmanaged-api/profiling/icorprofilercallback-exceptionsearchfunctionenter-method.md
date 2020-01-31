---
title: ICorProfilerCallback::ExceptionSearchFunctionEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
ms.openlocfilehash: c09d896e59a6c336fbe4923dbe85f30b039d8c36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866402"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="bd573-102">ICorProfilerCallback::ExceptionSearchFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="bd573-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="bd573-103">Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung begonnen hat, eine Funktion zu durchsuchen, um einen Handler für die aktuelle Ausnahme zu finden.</span><span class="sxs-lookup"><span data-stu-id="bd573-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd573-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd573-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd573-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="bd573-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="bd573-106">\[in] die ID der Funktion, die eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bd573-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="bd573-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd573-107">Requirements</span></span>  
 <span data-ttu-id="bd573-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd573-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd573-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd573-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd573-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd573-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd573-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd573-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd573-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd573-112">See also</span></span>

- [<span data-ttu-id="bd573-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd573-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bd573-114">ExceptionSearchFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="bd573-114">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
