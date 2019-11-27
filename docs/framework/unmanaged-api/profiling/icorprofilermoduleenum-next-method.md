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
ms.openlocfilehash: 361f08f8c787ad4c1288c56fb1bdb4d5136933e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442688"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="031ae-102">ICorProfilerModuleEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="031ae-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="031ae-103">Ruft die angegebene Anzahl von zusammenhängenden Modulen aus einer sequenziellen Auflistung von Modulen ab der Position ab, die der Enumerator aktuell in der Sequenz hat.</span><span class="sxs-lookup"><span data-stu-id="031ae-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="031ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="031ae-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="031ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="031ae-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="031ae-106">[in] Die Anzahl von abzurufenden Modulen.</span><span class="sxs-lookup"><span data-stu-id="031ae-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="031ae-107">[out] Ein Array von `ModuleID`-Werten, von denen jeder ein abgerufenes Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="031ae-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="031ae-108">[out] Ein Zeiger auf die Anzahl von Elementen, die tatsächlich im `ids`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="031ae-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="031ae-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="031ae-109">Return Value</span></span>  
 <span data-ttu-id="031ae-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="031ae-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="031ae-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="031ae-111">HRESULT</span></span>|<span data-ttu-id="031ae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="031ae-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="031ae-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="031ae-113">S_OK</span></span>|<span data-ttu-id="031ae-114">Es wurden `celt` Elemente zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="031ae-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="031ae-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="031ae-115">S_FALSE</span></span>|<span data-ttu-id="031ae-116">Es wurden weniger als `celt`-Elemente zurückgegeben, wodurch angegeben ist, dass die Enumeration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="031ae-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="031ae-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="031ae-117">Requirements</span></span>  
 <span data-ttu-id="031ae-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="031ae-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="031ae-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="031ae-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="031ae-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="031ae-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="031ae-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="031ae-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031ae-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="031ae-122">See also</span></span>

- [<span data-ttu-id="031ae-123">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="031ae-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="031ae-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="031ae-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
