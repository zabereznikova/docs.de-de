---
title: ICorProfilerObjectEnum::Clone-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea0484db53a94a3134b85f97b294c5eb7d1dc7e6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500563"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="e74ca-102">ICorProfilerObjectEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="e74ca-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="e74ca-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieses [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e74ca-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e74ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e74ca-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e74ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e74ca-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e74ca-106">[out] Ein Zeiger auf den Schnittstellenzeiger, der wiederum auf die Kopie dieses zeigt `ICorProfilerObjectEnum` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e74ca-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="e74ca-107">Die Kopie behält eine eigene Enumerationszustand getrennt von diesem.</span><span class="sxs-lookup"><span data-stu-id="e74ca-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="e74ca-108">Allerdings wird die Kopie in die ursprüngliche Cursorposition des Enumerators aktuellen Cursorposition bis identisch sein.</span><span class="sxs-lookup"><span data-stu-id="e74ca-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e74ca-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e74ca-109">Requirements</span></span>  
 <span data-ttu-id="e74ca-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e74ca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e74ca-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e74ca-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e74ca-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e74ca-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e74ca-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e74ca-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e74ca-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e74ca-114">See also</span></span>
- [<span data-ttu-id="e74ca-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e74ca-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
