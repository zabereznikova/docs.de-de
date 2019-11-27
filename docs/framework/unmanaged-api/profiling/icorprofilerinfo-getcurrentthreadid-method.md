---
title: ICorProfilerInfo::GetCurrentThreadID-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: fc5356f097f869403212cd234a508f1f29c5ec94
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450385"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="3aa3d-102">ICorProfilerInfo::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="3aa3d-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="3aa3d-103">Ruft die ID des aktuellen Threads ab, wenn es sich um einen verwalteten Thread handelt.</span><span class="sxs-lookup"><span data-stu-id="3aa3d-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3aa3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3aa3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3aa3d-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="3aa3d-106">vorgenommen Ein Zeiger auf die zurückgegebene ID des verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="3aa3d-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3aa3d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3aa3d-107">Remarks</span></span>  
 <span data-ttu-id="3aa3d-108">Wenn der aktuelle Thread ein interner Lauf Zeit Thread oder ein anderer nicht verwalteter Thread ist, gibt `GetCurrentThreadID` CORPROF_E_NOT_MANAGED_THREAD als HRESULT zurück, und der zurückgegebene Wert des `pThreadId`-Parameters ist NULL.</span><span class="sxs-lookup"><span data-stu-id="3aa3d-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa3d-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3aa3d-109">Requirements</span></span>  
 <span data-ttu-id="3aa3d-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aa3d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aa3d-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3aa3d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3aa3d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3aa3d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3aa3d-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa3d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa3d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3aa3d-114">See also</span></span>

- [<span data-ttu-id="3aa3d-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3aa3d-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
