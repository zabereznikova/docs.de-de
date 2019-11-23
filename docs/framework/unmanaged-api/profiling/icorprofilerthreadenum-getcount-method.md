---
title: ICorProfilerThreadEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
ms.openlocfilehash: 695b720119854de4645b2f14dd55811f2465504a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447640"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="0442f-102">ICorProfilerThreadEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="0442f-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="0442f-103">Ruft die Anzahl der Threads ab, die von der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0442f-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0442f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0442f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0442f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0442f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0442f-106">[out] The number of threads used by the application.</span><span class="sxs-lookup"><span data-stu-id="0442f-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0442f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0442f-107">Requirements</span></span>  
 <span data-ttu-id="0442f-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0442f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0442f-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0442f-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0442f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0442f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0442f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0442f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0442f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0442f-112">See also</span></span>

- [<span data-ttu-id="0442f-113">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0442f-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="0442f-114">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0442f-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
