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
ms.openlocfilehash: b48b782b7c8be35bfb815d72758f0bc316fb2114
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494721"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="b1929-102">ICorProfilerModuleEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="b1929-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="b1929-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="b1929-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1929-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1929-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1929-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b1929-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b1929-106">in Die Anzahl der Elemente, die übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b1929-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1929-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b1929-107">Return Value</span></span>  
 <span data-ttu-id="b1929-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1929-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b1929-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1929-109">HRESULT</span></span>|<span data-ttu-id="b1929-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b1929-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1929-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1929-111">S_OK</span></span>|<span data-ttu-id="b1929-112">`celt`Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="b1929-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="b1929-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b1929-113">S_FALSE</span></span>|<span data-ttu-id="b1929-114">Weniger als `celt` Elemente wurden übersprungen, was darauf hinweist, dass keine weiteren Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b1929-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1929-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b1929-115">Remarks</span></span>  
 <span data-ttu-id="b1929-116">Die neue Position des Cursors dieses Enumerators ist (aktuelle Position) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="b1929-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1929-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b1929-117">Requirements</span></span>  
 <span data-ttu-id="b1929-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1929-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1929-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1929-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1929-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1929-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1929-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1929-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1929-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b1929-122">See also</span></span>

- [<span data-ttu-id="b1929-123">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1929-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="b1929-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b1929-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
