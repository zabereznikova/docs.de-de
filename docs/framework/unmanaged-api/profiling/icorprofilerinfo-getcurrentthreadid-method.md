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
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863945"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="2f679-102">ICorProfilerInfo::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="2f679-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="2f679-103">Ruft die ID des aktuellen Threads ab, wenn es sich um einen verwalteten Thread handelt.</span><span class="sxs-lookup"><span data-stu-id="2f679-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f679-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f679-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f679-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2f679-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="2f679-106">vorgenommen Ein Zeiger auf die zurückgegebene ID des verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="2f679-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f679-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f679-107">Remarks</span></span>  
 <span data-ttu-id="2f679-108">Wenn der aktuelle Thread ein interner Lauf Zeit Thread oder ein anderer nicht verwalteter Thread ist, gibt `GetCurrentThreadID` CORPROF_E_NOT_MANAGED_THREAD als HRESULT zurück, und der zurückgegebene Wert des `pThreadId`-Parameters ist NULL.</span><span class="sxs-lookup"><span data-stu-id="2f679-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f679-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f679-109">Requirements</span></span>  
 <span data-ttu-id="2f679-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f679-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f679-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f679-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f679-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f679-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f679-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f679-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f679-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f679-114">See also</span></span>

- [<span data-ttu-id="2f679-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f679-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
