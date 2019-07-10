---
title: ICorProfilerFunctionEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6c1efe2a7d831f26556dbf501176f02588f2e0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780327"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="fbe21-102">ICorProfilerFunctionEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="fbe21-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="fbe21-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieses [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fbe21-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbe21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbe21-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbe21-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fbe21-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="fbe21-106">[out] Ein Zeiger auf den Schnittstellenzeiger, der, die wiederum auf eine Kopie dieses zeigt [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fbe21-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="fbe21-107">Die Kopie des Enumerators verwaltet einen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="fbe21-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="fbe21-108">Allerdings ist die Kopie in die ursprüngliche Cursorposition Cursorposition des Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="fbe21-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbe21-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbe21-109">Requirements</span></span>  
 <span data-ttu-id="fbe21-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbe21-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbe21-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fbe21-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fbe21-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbe21-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbe21-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbe21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe21-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbe21-114">See also</span></span>

- [<span data-ttu-id="fbe21-115">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbe21-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="fbe21-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fbe21-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
