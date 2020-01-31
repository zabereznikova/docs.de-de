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
ms.openlocfilehash: 7c1ee1c39fbf2dcc1f16df3bc94a235676a216dd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862567"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="b025a-102">ICorProfilerInfo2::GetThreadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="b025a-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="b025a-103">Ruft die ID der Anwendungsdomäne ab, in der der angegebene Thread aktuell Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="b025a-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b025a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b025a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b025a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b025a-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b025a-106">in Die ID, die den Thread angibt.</span><span class="sxs-lookup"><span data-stu-id="b025a-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="b025a-107">vorgenommen Ein Zeiger auf die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="b025a-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b025a-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b025a-108">Requirements</span></span>  
 <span data-ttu-id="b025a-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b025a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b025a-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b025a-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b025a-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b025a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b025a-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b025a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b025a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b025a-113">See also</span></span>

- [<span data-ttu-id="b025a-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b025a-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b025a-115">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b025a-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
