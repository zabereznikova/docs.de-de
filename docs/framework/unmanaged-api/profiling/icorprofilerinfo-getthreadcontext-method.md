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
ms.openlocfilehash: 2e24d72c8be1ace10b2feb15101ed8f83db386c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724090"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="dab80-102">ICorProfilerInfo::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="dab80-102">ICorProfilerInfo::GetThreadContext Method</span></span>

<span data-ttu-id="dab80-103">Ruft die Kontext Identität ab, die dem angegebenen Thread zurzeit zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dab80-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dab80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dab80-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dab80-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="dab80-106">in Die ID des Threads.</span><span class="sxs-lookup"><span data-stu-id="dab80-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="dab80-107">vorgenommen Ein Zeiger auf die Kontext-ID, die derzeit dem angegebenen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dab80-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="dab80-108">Wenn dem Thread aktuell kein Kontext zugeordnet ist, gibt diese Funktion CORPROF_E_DATAINCOMPLETE zurück.</span><span class="sxs-lookup"><span data-stu-id="dab80-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dab80-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dab80-109">Requirements</span></span>  

 <span data-ttu-id="dab80-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dab80-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dab80-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dab80-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dab80-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dab80-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dab80-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dab80-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab80-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dab80-114">See also</span></span>

- [<span data-ttu-id="dab80-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dab80-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
