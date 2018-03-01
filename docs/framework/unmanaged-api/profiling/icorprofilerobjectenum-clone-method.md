---
title: ICorProfilerObjectEnum::Clone-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d8e478eb9165b4aa5bf019f02f4f128931d928b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="df3fd-102">ICorProfilerObjectEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="df3fd-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="df3fd-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieser [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="df3fd-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df3fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df3fd-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df3fd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df3fd-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="df3fd-106">[out] Ein Zeiger auf den Schnittstellenzeiger, der wiederum auf die Kopie dieser zeigt `ICorProfilerObjectEnum` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="df3fd-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="df3fd-107">Die Kopie behält ihren eigenen Enumerationszustand separat von diesem.</span><span class="sxs-lookup"><span data-stu-id="df3fd-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="df3fd-108">Allerdings werden die Kopie ursprüngliche Cursorposition identisch mit der aktuellen Cursorposition des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="df3fd-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df3fd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df3fd-109">Requirements</span></span>  
 <span data-ttu-id="df3fd-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df3fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df3fd-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="df3fd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="df3fd-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df3fd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df3fd-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df3fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3fd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df3fd-114">See Also</span></span>  
 [<span data-ttu-id="df3fd-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df3fd-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
