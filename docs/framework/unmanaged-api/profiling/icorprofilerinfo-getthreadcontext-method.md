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
ms.openlocfilehash: f26fd93d42a709249936815d3c29ae572482f427
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224623"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="026a4-102">ICorProfilerInfo::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="026a4-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="026a4-103">Ruft die Kontextidentität, die derzeit mit dem angegebenen Thread zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="026a4-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="026a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="026a4-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="026a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="026a4-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="026a4-106">[in] Die ID des Threads.</span><span class="sxs-lookup"><span data-stu-id="026a4-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="026a4-107">[out] Ein Zeiger auf die Kontext-ID, die derzeit mit dem angegebenen Thread zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="026a4-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="026a4-108">Wenn der Thread ohne Kontext aktuell zugeordnet verfügt, gibt diese Funktion CORPROF_E_DATAINCOMPLETE zurück.</span><span class="sxs-lookup"><span data-stu-id="026a4-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="026a4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="026a4-109">Requirements</span></span>  
 <span data-ttu-id="026a4-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="026a4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="026a4-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="026a4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="026a4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="026a4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="026a4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="026a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="026a4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="026a4-114">See also</span></span>

- [<span data-ttu-id="026a4-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="026a4-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
