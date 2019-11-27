---
title: ICorProfilerCallback::ExceptionSearchCatcherFound-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
ms.openlocfilehash: 080777b656e1c3df1cc4170fe1dff6de6ddb41fc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445391"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="2ced4-102">ICorProfilerCallback::ExceptionSearchCatcherFound-Methode</span><span class="sxs-lookup"><span data-stu-id="2ced4-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="2ced4-103">Benachrichtigt den Profiler, dass die Such Phase der Ausnahmebehandlung einen Handler für die ausgelöste Ausnahme gefunden hat.</span><span class="sxs-lookup"><span data-stu-id="2ced4-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ced4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ced4-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ced4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ced4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2ced4-106">in Die ID der Funktion, die den Ausnahmehandler enthält.</span><span class="sxs-lookup"><span data-stu-id="2ced4-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ced4-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2ced4-107">Requirements</span></span>  
 <span data-ttu-id="2ced4-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ced4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ced4-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2ced4-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2ced4-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ced4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ced4-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ced4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ced4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ced4-112">See also</span></span>

- [<span data-ttu-id="2ced4-113">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ced4-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
