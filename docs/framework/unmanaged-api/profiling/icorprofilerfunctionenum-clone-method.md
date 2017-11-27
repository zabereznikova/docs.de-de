---
title: ICorProfilerFunctionEnum::Clone-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum.Clone Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dc1d14a1480c3634993190448f9beff911bebf6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="95236-102">ICorProfilerFunctionEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="95236-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="95236-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieser [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="95236-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95236-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95236-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95236-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95236-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="95236-106">[out] Ein Zeiger auf den Schnittstellenzeiger auf, die, die wiederum auf die Kopie von dieser verweist [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="95236-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="95236-107">Die Kopie des Enumerators behält ihren eigenen Enumerationszustand separat von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="95236-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="95236-108">Allerdings ist die ursprüngliche Cursorposition der Kopie identisch mit der aktuellen Cursorposition des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="95236-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95236-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95236-109">Requirements</span></span>  
 <span data-ttu-id="95236-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95236-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95236-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95236-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95236-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95236-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95236-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95236-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95236-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95236-114">See Also</span></span>  
 [<span data-ttu-id="95236-115">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95236-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="95236-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="95236-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
