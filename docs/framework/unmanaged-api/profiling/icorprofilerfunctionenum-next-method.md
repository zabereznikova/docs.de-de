---
title: ICorProfilerFunctionEnum::Next-Methode
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
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd9c01e014ee19c5e30fdc293d39787638e8b1d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="a4ea7-102">ICorProfilerFunctionEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a4ea7-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="a4ea7-103">Ruft die angegebene Anzahl von zusammenhängenden Funktionen aus einer sequenziellen Auflistung von Funktionen ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ea7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4ea7-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4ea7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4ea7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a4ea7-106">[in] Die Anzahl von abzurufenden Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="a4ea7-107">[out] Ein Array von `COR_PRF_FUNCTION`-Werten, von denen jeder eine abgerufene Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a4ea7-108">[out] Ein Zeiger auf die Anzahl von Funktionen, die tatsächlich im `ids`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4ea7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a4ea7-109">Return Value</span></span>  
 <span data-ttu-id="a4ea7-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a4ea7-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4ea7-111">HRESULT</span></span>|<span data-ttu-id="a4ea7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4ea7-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4ea7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4ea7-113">S_OK</span></span>|<span data-ttu-id="a4ea7-114">`celt` Elemente wurden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="a4ea7-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a4ea7-115">S_FALSE</span></span>|<span data-ttu-id="a4ea7-116">Es wurden weniger als `celt`-Elemente zurückgegeben, wodurch angegeben ist, dass die Enumeration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a4ea7-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4ea7-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4ea7-117">Requirements</span></span>  
 <span data-ttu-id="a4ea7-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4ea7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4ea7-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4ea7-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4ea7-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4ea7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4ea7-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4ea7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ea7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4ea7-122">See Also</span></span>  
 [<span data-ttu-id="a4ea7-123">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4ea7-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="a4ea7-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4ea7-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
