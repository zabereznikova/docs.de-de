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
ms.openlocfilehash: f8eff85392d355ea54980ac6b29e3c4cebb1b240
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869594"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="868c5-102">ICorProfilerInfo::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="868c5-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="868c5-103">Ruft die Kontext Identität ab, die dem angegebenen Thread zurzeit zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="868c5-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="868c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="868c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="868c5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="868c5-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="868c5-106">in Die ID des Threads.</span><span class="sxs-lookup"><span data-stu-id="868c5-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="868c5-107">vorgenommen Ein Zeiger auf die Kontext-ID, die derzeit dem angegebenen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="868c5-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="868c5-108">Wenn dem Thread aktuell kein Kontext zugeordnet ist, gibt diese Funktion CORPROF_E_DATAINCOMPLETE zurück.</span><span class="sxs-lookup"><span data-stu-id="868c5-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="868c5-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="868c5-109">Requirements</span></span>  
 <span data-ttu-id="868c5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="868c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="868c5-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="868c5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="868c5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="868c5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="868c5-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="868c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868c5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="868c5-114">See also</span></span>

- [<span data-ttu-id="868c5-115">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="868c5-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
