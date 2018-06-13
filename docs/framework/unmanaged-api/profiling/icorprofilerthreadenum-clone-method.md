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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84a71ac3a1ba30e20bb6ec7e6a0e31db9d3b5738
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455705"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="98b59-102">ICorProfilerThreadEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="98b59-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="98b59-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieser [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="98b59-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98b59-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98b59-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="98b59-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="98b59-106">[out] Ein Zeiger auf den Schnittstellenzeiger auf, die, die wiederum auf die Kopie von dieser verweist [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="98b59-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="98b59-107">Die Kopie des Enumerators behält ihren eigenen Enumerationszustand separat von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="98b59-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="98b59-108">Allerdings ist die ursprüngliche Cursorposition der Kopie dieser aktuellen Cursorposition des Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="98b59-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98b59-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98b59-109">Requirements</span></span>  
 <span data-ttu-id="98b59-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98b59-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98b59-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98b59-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98b59-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98b59-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98b59-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98b59-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b59-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98b59-114">See Also</span></span>  
 [<span data-ttu-id="98b59-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="98b59-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="98b59-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="98b59-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
