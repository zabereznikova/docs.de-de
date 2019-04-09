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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57d8279ba9733e6a381d445d50df56b415353a16
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077146"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="09343-102">ICorProfilerModuleEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="09343-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="09343-103">Ruft die angegebene Anzahl von zusammenhängenden Modulen aus einer sequenziellen Auflistung von Modulen ab der Position ab, die der Enumerator aktuell in der Sequenz hat.</span><span class="sxs-lookup"><span data-stu-id="09343-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09343-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09343-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09343-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="09343-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="09343-106">[in] Die Anzahl von abzurufenden Modulen.</span><span class="sxs-lookup"><span data-stu-id="09343-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="09343-107">[out] Ein Array von `ModuleID`-Werten, von denen jeder ein abgerufenes Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="09343-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="09343-108">[out] Ein Zeiger auf die Anzahl von Elementen, die tatsächlich im `ids`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="09343-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09343-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="09343-109">Return Value</span></span>  
 <span data-ttu-id="09343-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="09343-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09343-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09343-111">HRESULT</span></span>|<span data-ttu-id="09343-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09343-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09343-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="09343-113">S_OK</span></span>|`celt` <span data-ttu-id="09343-114">Elemente wurden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="09343-114">elements were returned.</span></span>|  
|<span data-ttu-id="09343-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="09343-115">S_FALSE</span></span>|<span data-ttu-id="09343-116">Es wurden weniger als `celt`-Elemente zurückgegeben, wodurch angegeben ist, dass die Enumeration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="09343-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09343-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09343-117">Requirements</span></span>  
 <span data-ttu-id="09343-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09343-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09343-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09343-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09343-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09343-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="09343-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="09343-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="09343-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09343-122">See also</span></span>

- [<span data-ttu-id="09343-123">ICorProfilerModuleEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09343-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="09343-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="09343-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
