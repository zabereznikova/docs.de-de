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
ms.openlocfilehash: 022d0d9c86e4b3b9924b8a486166d8ce3b71e42c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781194"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="bc2d0-102">ICorProfilerThreadEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="bc2d0-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="bc2d0-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieses [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc2d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc2d0-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc2d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc2d0-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="bc2d0-106">[out] Ein Zeiger auf den Schnittstellenzeiger, der, die wiederum auf eine Kopie dieses zeigt [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="bc2d0-107">Die Kopie des Enumerators verwaltet einen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="bc2d0-108">Allerdings ist die ursprüngliche Cursorposition der Kopie dieses aktuellen Cursorposition des Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="bc2d0-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc2d0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc2d0-109">Requirements</span></span>  
 <span data-ttu-id="bc2d0-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc2d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc2d0-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc2d0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc2d0-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc2d0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc2d0-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc2d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc2d0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc2d0-114">See also</span></span>

- [<span data-ttu-id="bc2d0-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="bc2d0-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="bc2d0-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc2d0-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
