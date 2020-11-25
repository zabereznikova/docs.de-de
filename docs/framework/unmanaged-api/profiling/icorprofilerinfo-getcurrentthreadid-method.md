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
ms.openlocfilehash: 18298c4c726d7d850e67afbf82ca77b7511d8917
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722588"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="74f55-102">ICorProfilerInfo::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="74f55-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>

<span data-ttu-id="74f55-103">Ruft die ID des aktuellen Threads ab, wenn es sich um einen verwalteten Thread handelt.</span><span class="sxs-lookup"><span data-stu-id="74f55-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74f55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74f55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="74f55-105">Parameters</span></span>  

 `pThreadId`  
 <span data-ttu-id="74f55-106">vorgenommen Ein Zeiger auf die zurückgegebene ID des verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="74f55-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74f55-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74f55-107">Remarks</span></span>  

 <span data-ttu-id="74f55-108">Wenn der aktuelle Thread ein interner Lauf Zeit Thread oder ein anderer nicht verwalteter Thread ist, wird `GetCurrentThreadID` CORPROF_E_NOT_MANAGED_THREAD als HRESULT zurückgegeben, und der zurückgegebene Wert des- `pThreadId` Parameters ist NULL.</span><span class="sxs-lookup"><span data-stu-id="74f55-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74f55-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="74f55-109">Requirements</span></span>  

 <span data-ttu-id="74f55-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74f55-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f55-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74f55-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74f55-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74f55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74f55-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f55-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74f55-114">See also</span></span>

- [<span data-ttu-id="74f55-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74f55-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
