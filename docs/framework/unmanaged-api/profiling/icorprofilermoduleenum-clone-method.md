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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd3e3739ea9b5330f456156c0455009d90478649
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470470"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="c445f-102">ICorProfilerModuleEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="c445f-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="c445f-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieses [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c445f-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c445f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c445f-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c445f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c445f-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c445f-106">[out] Ein Zeiger auf den Schnittstellenzeiger, der wiederum auf die Kopie dieses zeigt [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c445f-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="c445f-107">Die Kopie des Enumerators verwaltet einen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c445f-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="c445f-108">Allerdings ist die Kopie in die ursprüngliche Cursorposition Cursorposition des Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="c445f-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c445f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c445f-109">Requirements</span></span>  
 <span data-ttu-id="c445f-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c445f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c445f-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c445f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c445f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c445f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c445f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c445f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c445f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c445f-114">See also</span></span>
- [<span data-ttu-id="c445f-115">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c445f-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="c445f-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c445f-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
