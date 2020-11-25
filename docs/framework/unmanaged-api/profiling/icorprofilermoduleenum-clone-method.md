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
ms.openlocfilehash: ae9f6b7865a80e3edc4cae8fd1298e5eed864377
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722829"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="6030c-102">ICorProfilerModuleEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="6030c-102">ICorProfilerModuleEnum::Clone Method</span></span>

<span data-ttu-id="6030c-103">Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) -Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="6030c-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6030c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6030c-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6030c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6030c-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="6030c-106">vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) -Schnittstelle zeigt.</span><span class="sxs-lookup"><span data-stu-id="6030c-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="6030c-107">Die Kopie des Enumerators behält seinen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="6030c-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="6030c-108">Die ursprüngliche Cursorposition des Kopierens ist jedoch mit der aktuellen Cursorposition dieses Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="6030c-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6030c-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6030c-109">Requirements</span></span>  

 <span data-ttu-id="6030c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6030c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6030c-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6030c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6030c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6030c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6030c-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6030c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6030c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6030c-114">See also</span></span>

- [<span data-ttu-id="6030c-115">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6030c-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="6030c-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6030c-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
