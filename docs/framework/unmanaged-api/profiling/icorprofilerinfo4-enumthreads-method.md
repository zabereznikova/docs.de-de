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
ms.openlocfilehash: 5bea1b75e94d8011d3582d4f07d36bbc7a560502
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862216"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="183d1-102">ICorProfilerInfo4::EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="183d1-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="183d1-103">Gibt einen Enumerator zurück, der Methoden zum sequenziellen durchlaufen der Auflistung aller verwalteten Threads im Profil Erstellungs Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="183d1-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="183d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="183d1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="183d1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="183d1-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="183d1-106">vorgenommen Ein Zeiger auf eine [icorprofilerthreaderum](icorprofilerthreadenum-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="183d1-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="183d1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="183d1-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="183d1-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="183d1-108">Requirements</span></span>  
 <span data-ttu-id="183d1-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="183d1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="183d1-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="183d1-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="183d1-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="183d1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="183d1-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="183d1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="183d1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="183d1-113">See also</span></span>

- [<span data-ttu-id="183d1-114">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="183d1-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="183d1-115">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="183d1-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="183d1-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="183d1-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="183d1-117">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="183d1-117">Profiling</span></span>](index.md)
