---
title: ICorProfilerModuleEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: ccbb051ac30fb25199ce12c16fff74bb0b9944fa
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495085"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="c04fc-102">ICorProfilerModuleEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="c04fc-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="c04fc-103">Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) -Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="c04fc-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c04fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c04fc-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c04fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c04fc-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c04fc-106">vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) -Schnittstelle zeigt.</span><span class="sxs-lookup"><span data-stu-id="c04fc-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="c04fc-107">Die Kopie des Enumerators behält seinen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c04fc-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="c04fc-108">Die ursprüngliche Cursorposition des Kopierens ist jedoch mit der aktuellen Cursorposition dieses Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="c04fc-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c04fc-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c04fc-109">Requirements</span></span>  
 <span data-ttu-id="c04fc-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c04fc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c04fc-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c04fc-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c04fc-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c04fc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c04fc-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c04fc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04fc-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c04fc-114">See also</span></span>

- [<span data-ttu-id="c04fc-115">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c04fc-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="c04fc-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c04fc-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
