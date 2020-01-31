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
ms.openlocfilehash: a6b36883ec0914426b4f4c937390c1622faead25
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868290"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="41a5d-102">ICorProfilerModuleEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="41a5d-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="41a5d-103">Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) -Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="41a5d-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a5d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41a5d-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41a5d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="41a5d-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="41a5d-106">vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) -Schnittstelle zeigt.</span><span class="sxs-lookup"><span data-stu-id="41a5d-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="41a5d-107">Die Kopie des Enumerators behält seinen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="41a5d-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="41a5d-108">Die ursprüngliche Cursorposition des Kopierens ist jedoch mit der aktuellen Cursorposition dieses Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="41a5d-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a5d-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41a5d-109">Requirements</span></span>  
 <span data-ttu-id="41a5d-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41a5d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41a5d-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41a5d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41a5d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41a5d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41a5d-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41a5d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a5d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41a5d-114">See also</span></span>

- [<span data-ttu-id="41a5d-115">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41a5d-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="41a5d-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41a5d-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
