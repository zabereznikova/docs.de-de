---
title: ICorProfilerThreadEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: ca29655d1d0eb819dfe8b5f9910cd20ef47843c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441529"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="acf00-102">ICorProfilerThreadEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="acf00-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="acf00-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="acf00-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acf00-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acf00-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acf00-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="acf00-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="acf00-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="acf00-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span><span class="sxs-lookup"><span data-stu-id="acf00-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="acf00-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span><span class="sxs-lookup"><span data-stu-id="acf00-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf00-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acf00-109">Requirements</span></span>  
 <span data-ttu-id="acf00-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf00-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf00-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="acf00-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="acf00-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acf00-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acf00-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf00-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf00-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acf00-114">See also</span></span>

- [<span data-ttu-id="acf00-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="acf00-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="acf00-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="acf00-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
