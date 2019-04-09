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
ms.openlocfilehash: 14e8086532eff5dba6883575cc2daf447a32343a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182363"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="5a525-102">ICorProfilerObjectEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="5a525-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="5a525-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieses [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5a525-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a525-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a525-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a525-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a525-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5a525-106">[out] Ein Zeiger auf den Schnittstellenzeiger, der wiederum auf die Kopie dieses zeigt `ICorProfilerObjectEnum` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5a525-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="5a525-107">Die Kopie behält eine eigene Enumerationszustand getrennt von diesem.</span><span class="sxs-lookup"><span data-stu-id="5a525-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="5a525-108">Allerdings wird die Kopie in die ursprüngliche Cursorposition des Enumerators aktuellen Cursorposition bis identisch sein.</span><span class="sxs-lookup"><span data-stu-id="5a525-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a525-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a525-109">Requirements</span></span>  
 <span data-ttu-id="5a525-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a525-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a525-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a525-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a525-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a525-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5a525-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5a525-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a525-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a525-114">See also</span></span>

- [<span data-ttu-id="5a525-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a525-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
