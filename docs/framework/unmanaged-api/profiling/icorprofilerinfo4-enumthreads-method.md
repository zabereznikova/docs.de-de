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
ms.openlocfilehash: 6c394690f6c8d7f3618b385b0a1432fc396fb819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458019"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="0cb70-102">ICorProfilerInfo4::EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="0cb70-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="0cb70-103">Gibt einen Enumerator, der Methoden zum sequenziellen iterieren durch die Auflistung aller verwalteten Threads im profilierten Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0cb70-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cb70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cb70-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0cb70-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cb70-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="0cb70-106">[out] Ein Zeiger auf ein [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0cb70-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cb70-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cb70-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cb70-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cb70-108">Requirements</span></span>  
 <span data-ttu-id="0cb70-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cb70-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cb70-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0cb70-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0cb70-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cb70-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cb70-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cb70-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb70-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cb70-113">See Also</span></span>  
 [<span data-ttu-id="0cb70-114">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cb70-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="0cb70-115">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0cb70-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="0cb70-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0cb70-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="0cb70-117">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="0cb70-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
