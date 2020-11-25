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
ms.openlocfilehash: 092c3b328887b7d36ead77c64d31310b614b616a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707528"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="ceae0-102">ICorProfilerFunctionEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="ceae0-102">ICorProfilerFunctionEnum::Clone Method</span></span>

<span data-ttu-id="ceae0-103">Ruft einen Schnittstellen Zeiger auf eine Kopie dieser [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) -Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="ceae0-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceae0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ceae0-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceae0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ceae0-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="ceae0-106">vorgenommen Ein Zeiger auf den Schnittstellen Zeiger, der wiederum auf die Kopie dieser [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) -Schnittstelle zeigt.</span><span class="sxs-lookup"><span data-stu-id="ceae0-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="ceae0-107">Die Kopie des Enumerators behält seinen eigenen Enumerationszustand getrennt von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="ceae0-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="ceae0-108">Die ursprüngliche Cursorposition des Kopierens ist jedoch mit der aktuellen Cursorposition dieses Enumerators identisch.</span><span class="sxs-lookup"><span data-stu-id="ceae0-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceae0-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ceae0-109">Requirements</span></span>  

 <span data-ttu-id="ceae0-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ceae0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceae0-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ceae0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ceae0-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceae0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceae0-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceae0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceae0-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ceae0-114">See also</span></span>

- [<span data-ttu-id="ceae0-115">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ceae0-115">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="ceae0-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ceae0-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
