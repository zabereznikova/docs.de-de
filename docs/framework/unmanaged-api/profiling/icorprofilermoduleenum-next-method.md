---
title: ICorProfilerModuleEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
ms.openlocfilehash: 7a3ad94a4149d6ebb70e077926771e28d7f82779
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494838"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="1e9b8-102">ICorProfilerModuleEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="1e9b8-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="1e9b8-103">Ruft die angegebene Anzahl von zusammenhängenden Modulen aus einer sequenziellen Auflistung von Modulen ab der Position ab, die der Enumerator aktuell in der Sequenz hat.</span><span class="sxs-lookup"><span data-stu-id="1e9b8-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e9b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e9b8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e9b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e9b8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1e9b8-106">[in] Die Anzahl von abzurufenden Modulen.</span><span class="sxs-lookup"><span data-stu-id="1e9b8-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="1e9b8-107">[out] Ein Array von `ModuleID`-Werten, von denen jeder ein abgerufenes Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e9b8-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1e9b8-108">[out] Ein Zeiger auf die Anzahl von Elementen, die tatsächlich im `ids`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1e9b8-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e9b8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1e9b8-109">Return Value</span></span>  
 <span data-ttu-id="1e9b8-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e9b8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1e9b8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e9b8-111">HRESULT</span></span>|<span data-ttu-id="1e9b8-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e9b8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e9b8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e9b8-113">S_OK</span></span>|<span data-ttu-id="1e9b8-114">`celt` Elemente wurden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e9b8-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="1e9b8-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="1e9b8-115">S_FALSE</span></span>|<span data-ttu-id="1e9b8-116">Es wurden weniger als `celt`-Elemente zurückgegeben, wodurch angegeben ist, dass die Enumeration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1e9b8-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e9b8-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1e9b8-117">Requirements</span></span>  
 <span data-ttu-id="1e9b8-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e9b8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e9b8-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e9b8-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e9b8-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e9b8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e9b8-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e9b8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9b8-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="1e9b8-122">See also</span></span>

- [<span data-ttu-id="1e9b8-123">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e9b8-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="1e9b8-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1e9b8-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
