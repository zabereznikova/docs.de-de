---
title: ICorProfilerInfo2::GetThreadAppDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetThreadAppDomain
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4c8e16bc3d0a886e44bded3c274e5c53b43d75ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="9a7cf-102">ICorProfilerInfo2::GetThreadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="9a7cf-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="9a7cf-103">Ruft die ID der Anwendungsdomäne, in der der angegebene Thread gerade Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="9a7cf-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a7cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a7cf-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a7cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a7cf-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="9a7cf-106">[in] Die ID des Threads angibt.</span><span class="sxs-lookup"><span data-stu-id="9a7cf-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="9a7cf-107">[out] Ein Zeiger auf die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="9a7cf-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a7cf-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a7cf-108">Requirements</span></span>  
 <span data-ttu-id="9a7cf-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a7cf-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a7cf-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a7cf-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a7cf-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a7cf-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a7cf-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a7cf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a7cf-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a7cf-113">See Also</span></span>  
 [<span data-ttu-id="9a7cf-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a7cf-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="9a7cf-115">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a7cf-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
