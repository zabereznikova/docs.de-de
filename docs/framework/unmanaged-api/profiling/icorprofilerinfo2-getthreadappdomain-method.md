---
title: ICorProfilerInfo2::GetThreadAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fa4b1c45b7bf10d167089f80686f438d54288cf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782225"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="8184e-102">ICorProfilerInfo2::GetThreadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="8184e-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="8184e-103">Ruft die ID der Anwendungsdomäne, in der Code derzeit von der angegebene Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8184e-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8184e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8184e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8184e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8184e-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="8184e-106">[in] Die ID des Threads angibt.</span><span class="sxs-lookup"><span data-stu-id="8184e-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="8184e-107">[out] Ein Zeiger auf die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="8184e-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8184e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8184e-108">Requirements</span></span>  
 <span data-ttu-id="8184e-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8184e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8184e-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8184e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8184e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8184e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8184e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8184e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8184e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8184e-113">See also</span></span>

- [<span data-ttu-id="8184e-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8184e-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="8184e-115">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8184e-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
