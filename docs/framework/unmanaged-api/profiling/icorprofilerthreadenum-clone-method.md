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
ms.openlocfilehash: 890bb9bdd3b639d38f4f290eed86ad72b6a53f0f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494448"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="c2795-102">ICorProfilerThreadEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="c2795-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="c2795-103">Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [icorprofilerthreadenum](icorprofilerthreadenum-interface.md) -Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="c2795-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2795-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2795-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2795-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2795-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c2795-106">vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser [icorprofilerthreadenum](icorprofilerthreadenum-interface.md) -Schnittstelle zeigt.</span><span class="sxs-lookup"><span data-stu-id="c2795-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="c2795-107">Die Kopie des Enumerators behält seinen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c2795-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="c2795-108">Die ursprüngliche Cursorposition der Kopie ist jedoch mit der aktuellen Cursorposition des Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="c2795-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2795-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c2795-109">Requirements</span></span>  
 <span data-ttu-id="c2795-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2795-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2795-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2795-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2795-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2795-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2795-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2795-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2795-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c2795-114">See also</span></span>

- [<span data-ttu-id="c2795-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="c2795-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="c2795-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c2795-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
