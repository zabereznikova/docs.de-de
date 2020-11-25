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
ms.openlocfilehash: dc8e85c5a6047ad5dd99520b57789605333d5bf2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721204"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="61ab3-102">ICorProfilerThreadEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="61ab3-102">ICorProfilerThreadEnum::Next Method</span></span>

<span data-ttu-id="61ab3-103">Ruft die angegebene Anzahl von zusammenhängenden Threads aus einer sequenziellen Auflistung von Threads ab der Position ab, die der Enumerator aktuell in der Sequenz hat.</span><span class="sxs-lookup"><span data-stu-id="61ab3-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ab3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61ab3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61ab3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61ab3-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="61ab3-106">[in] Die Anzahl von abzurufenden Threads.</span><span class="sxs-lookup"><span data-stu-id="61ab3-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="61ab3-107">[out] Ein Array von `ThreadID`-Werten, von denen jeder einen abgerufenen Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="61ab3-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="61ab3-108">[out] Ein Zeiger auf die Anzahl von Threads, die tatsächlich im `ids`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="61ab3-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61ab3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61ab3-109">Return Value</span></span>  

 <span data-ttu-id="61ab3-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="61ab3-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="61ab3-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61ab3-111">HRESULT</span></span>|<span data-ttu-id="61ab3-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="61ab3-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61ab3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="61ab3-113">S_OK</span></span>|<span data-ttu-id="61ab3-114">`celt` Elemente wurden zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="61ab3-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="61ab3-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="61ab3-115">S_FALSE</span></span>|<span data-ttu-id="61ab3-116">Es wurden weniger als `celt`-Elemente zurückgegeben, wodurch angegeben ist, dass die Enumeration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="61ab3-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61ab3-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="61ab3-117">Requirements</span></span>  

 <span data-ttu-id="61ab3-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61ab3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61ab3-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="61ab3-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="61ab3-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61ab3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61ab3-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61ab3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ab3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61ab3-122">See also</span></span>

- [<span data-ttu-id="61ab3-123">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61ab3-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="61ab3-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="61ab3-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
