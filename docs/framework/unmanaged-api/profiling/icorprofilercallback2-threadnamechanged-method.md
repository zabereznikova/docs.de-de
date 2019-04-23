---
title: ICorProfilerCallback2::ThreadNameChanged-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dbd9374decdce171d45e57512470c652abc24882
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173669"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="fc5cb-102">ICorProfilerCallback2::ThreadNameChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="fc5cb-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="fc5cb-103">Benachrichtigt den Profiler, dass der Name eines Threads geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="fc5cb-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc5cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc5cb-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc5cb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc5cb-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="fc5cb-106">[in] Die ID des Threads.</span><span class="sxs-lookup"><span data-stu-id="fc5cb-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fc5cb-107">[in] Die Länge des neuen Namens des Threads.</span><span class="sxs-lookup"><span data-stu-id="fc5cb-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="fc5cb-108">[in] Der neue Name des Threads.</span><span class="sxs-lookup"><span data-stu-id="fc5cb-108">[in] The new name of the thread.</span></span> <span data-ttu-id="fc5cb-109">Der Name ist kein Null-terminiert.</span><span class="sxs-lookup"><span data-stu-id="fc5cb-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc5cb-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fc5cb-110">Requirements</span></span>  
 <span data-ttu-id="fc5cb-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc5cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc5cb-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fc5cb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fc5cb-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc5cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc5cb-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc5cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5cb-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc5cb-115">See also</span></span>

- [<span data-ttu-id="fc5cb-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc5cb-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fc5cb-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc5cb-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
