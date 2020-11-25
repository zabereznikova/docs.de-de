---
title: ICorProfilerObjectEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 83c6af74ebc3eb668317bd64628af17513a2aed6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702354"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="f125e-102">ICorProfilerObjectEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="f125e-102">ICorProfilerObjectEnum::Skip Method</span></span>

<span data-ttu-id="f125e-103">Verschiebt den Cursor dieses Enumerators von seiner aktuellen Position, sodass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="f125e-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f125e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f125e-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f125e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f125e-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f125e-106">in Die Anzahl der Elemente, die übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f125e-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f125e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f125e-107">Remarks</span></span>  

 <span data-ttu-id="f125e-108">Die neue Position des Cursors dieses Enumerators ist: (aktuelle Position) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="f125e-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f125e-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f125e-109">Requirements</span></span>  

 <span data-ttu-id="f125e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f125e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f125e-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f125e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f125e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f125e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f125e-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f125e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f125e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f125e-114">See also</span></span>

- [<span data-ttu-id="f125e-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f125e-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
