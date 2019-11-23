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
ms.openlocfilehash: 1149298b4c5e521b37aae6ec48d463f395f18ae3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439560"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="e85d5-102">ICorProfilerCallback2::ThreadNameChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="e85d5-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="e85d5-103">Notifies the code profiler that the name of a thread has changed.</span><span class="sxs-lookup"><span data-stu-id="e85d5-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e85d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e85d5-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e85d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e85d5-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e85d5-106">[in] The ID of the thread.</span><span class="sxs-lookup"><span data-stu-id="e85d5-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e85d5-107">[in] The length of the new name of the thread.</span><span class="sxs-lookup"><span data-stu-id="e85d5-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="e85d5-108">[in] The new name of the thread.</span><span class="sxs-lookup"><span data-stu-id="e85d5-108">[in] The new name of the thread.</span></span> <span data-ttu-id="e85d5-109">The name is not null-terminated.</span><span class="sxs-lookup"><span data-stu-id="e85d5-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e85d5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e85d5-110">Requirements</span></span>  
 <span data-ttu-id="e85d5-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e85d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e85d5-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e85d5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e85d5-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e85d5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e85d5-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e85d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85d5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e85d5-115">See also</span></span>

- [<span data-ttu-id="e85d5-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e85d5-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e85d5-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e85d5-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
