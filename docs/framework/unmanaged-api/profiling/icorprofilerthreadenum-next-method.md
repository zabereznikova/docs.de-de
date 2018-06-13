---
title: ICorProfilerThreadEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed01b2f59c46d1dcedd62846ea663c9aa7213b37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457725"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="d2f69-102">ICorProfilerThreadEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="d2f69-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="d2f69-103">Ruft die angegebene Anzahl von zusammenhängenden Threads aus einer sequenziellen Auflistung von Threads ab der Position ab, die der Enumerator aktuell in der Sequenz hat.</span><span class="sxs-lookup"><span data-stu-id="d2f69-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2f69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2f69-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2f69-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2f69-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d2f69-106">[in] Die Anzahl von abzurufenden Threads.</span><span class="sxs-lookup"><span data-stu-id="d2f69-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="d2f69-107">[out] Ein Array von `ThreadID`-Werten, von denen jeder einen abgerufenen Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2f69-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d2f69-108">[out] Ein Zeiger auf die Anzahl von Threads, die tatsächlich im `ids`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d2f69-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2f69-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2f69-109">Return Value</span></span>  
 <span data-ttu-id="d2f69-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d2f69-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d2f69-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2f69-111">HRESULT</span></span>|<span data-ttu-id="d2f69-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2f69-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d2f69-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2f69-113">S_OK</span></span>|<span data-ttu-id="d2f69-114">`celt` Elemente wurden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d2f69-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="d2f69-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d2f69-115">S_FALSE</span></span>|<span data-ttu-id="d2f69-116">Es wurden weniger als `celt`-Elemente zurückgegeben, wodurch angegeben ist, dass die Enumeration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d2f69-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2f69-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2f69-117">Requirements</span></span>  
 <span data-ttu-id="d2f69-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2f69-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2f69-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2f69-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2f69-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2f69-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2f69-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2f69-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f69-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2f69-122">See Also</span></span>  
 [<span data-ttu-id="d2f69-123">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2f69-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="d2f69-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d2f69-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
