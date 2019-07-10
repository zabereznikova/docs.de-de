---
title: ICorProfilerModuleEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eecb2a5da9dddaccbab7fcc6d74af6e4c6bfb72c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775125"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="5bde6-102">ICorProfilerModuleEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="5bde6-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="5bde6-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="5bde6-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bde6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bde6-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bde6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5bde6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5bde6-106">[in] Die Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5bde6-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bde6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5bde6-107">Return Value</span></span>  
 <span data-ttu-id="5bde6-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5bde6-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5bde6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5bde6-109">HRESULT</span></span>|<span data-ttu-id="5bde6-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bde6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bde6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bde6-111">S_OK</span></span>|<span data-ttu-id="5bde6-112">`celt` -Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="5bde6-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="5bde6-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5bde6-113">S_FALSE</span></span>|<span data-ttu-id="5bde6-114">Weniger als `celt` Elemente übersprungen wurden, was bedeutet, dass keine Elemente mehr vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5bde6-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bde6-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5bde6-115">Remarks</span></span>  
 <span data-ttu-id="5bde6-116">Die neue Position der Cursor des Enumerators ist (aktuelle Position) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="5bde6-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bde6-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5bde6-117">Requirements</span></span>  
 <span data-ttu-id="5bde6-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bde6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bde6-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bde6-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bde6-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bde6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bde6-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bde6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bde6-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bde6-122">See also</span></span>

- [<span data-ttu-id="5bde6-123">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bde6-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="5bde6-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5bde6-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
