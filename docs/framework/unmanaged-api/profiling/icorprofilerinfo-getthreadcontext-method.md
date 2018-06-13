---
title: ICorProfilerInfo::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acb4d67f41b1434fe8052a74e976907f24fecd31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453576"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="657e8-102">ICorProfilerInfo::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="657e8-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="657e8-103">Ruft die Kontextidentität, die derzeit zugewiesen ist, mit dem angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="657e8-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="657e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="657e8-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="657e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="657e8-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="657e8-106">[in] Die ID des Threads.</span><span class="sxs-lookup"><span data-stu-id="657e8-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="657e8-107">[out] Ein Zeiger auf die Kontext-ID, die derzeit mit dem angegebenen Thread zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="657e8-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="657e8-108">Wenn der Thread kein Kontext derzeit zugeordnet verfügt, wird diese Funktion CORPROF_E_DATAINCOMPLETE zurück.</span><span class="sxs-lookup"><span data-stu-id="657e8-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="657e8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="657e8-109">Requirements</span></span>  
 <span data-ttu-id="657e8-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="657e8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="657e8-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="657e8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="657e8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="657e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="657e8-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="657e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657e8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="657e8-114">See Also</span></span>  
 [<span data-ttu-id="657e8-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="657e8-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
