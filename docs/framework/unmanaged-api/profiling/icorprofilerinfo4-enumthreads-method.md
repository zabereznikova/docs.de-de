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
ms.openlocfilehash: df0e66c8563404d7de4f1e11f41483f2f61f519c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721555"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="a7168-102">ICorProfilerInfo4::EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a7168-102">ICorProfilerInfo4::EnumThreads Method</span></span>

<span data-ttu-id="a7168-103">Gibt einen Enumerator zurück, der Methoden zum sequenziellen durchlaufen der Auflistung aller verwalteten Threads im Profil Erstellungs Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a7168-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7168-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7168-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7168-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7168-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="a7168-106">vorgenommen Ein Zeiger auf eine [icorprofilerthreaderum](icorprofilerthreadenum-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a7168-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7168-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a7168-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7168-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a7168-108">Requirements</span></span>  

 <span data-ttu-id="a7168-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7168-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7168-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7168-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7168-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7168-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7168-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7168-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7168-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7168-113">See also</span></span>

- [<span data-ttu-id="a7168-114">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7168-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="a7168-115">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7168-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="a7168-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a7168-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a7168-117">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="a7168-117">Profiling</span></span>](index.md)
