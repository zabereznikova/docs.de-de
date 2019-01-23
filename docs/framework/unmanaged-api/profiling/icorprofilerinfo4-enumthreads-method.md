---
title: ICorProfilerInfo4::EnumThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8cfb474eaa0a770c2bb101787d34072e4ed98714
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501736"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="f5167-102">ICorProfilerInfo4::EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f5167-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="f5167-103">Gibt einen Enumerator, der Methoden, um Sie sequenziell zu durchlaufen, bis die Auflistung aller verwalteten Threads im profilierten Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f5167-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5167-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5167-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5167-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5167-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f5167-106">[out] Ein Zeiger auf ein [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f5167-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5167-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5167-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5167-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5167-108">Requirements</span></span>  
 <span data-ttu-id="f5167-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5167-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5167-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5167-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5167-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5167-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5167-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5167-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5167-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5167-113">See also</span></span>
- [<span data-ttu-id="f5167-114">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5167-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="f5167-115">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5167-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="f5167-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f5167-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f5167-117">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="f5167-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
