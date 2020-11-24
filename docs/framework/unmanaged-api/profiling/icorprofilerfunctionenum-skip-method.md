---
title: ICorProfilerFunctionEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: da578e02db0744b1f64c1d392844aa020721e784
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669254"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="f7e36-102">ICorProfilerFunctionEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="f7e36-102">ICorProfilerFunctionEnum::Skip Method</span></span>

<span data-ttu-id="f7e36-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="f7e36-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7e36-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7e36-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7e36-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="f7e36-106">in Die Anzahl der Elemente, die übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f7e36-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7e36-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f7e36-107">Return Value</span></span>  

 <span data-ttu-id="f7e36-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f7e36-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f7e36-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7e36-109">HRESULT</span></span>|<span data-ttu-id="f7e36-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f7e36-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7e36-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7e36-111">S_OK</span></span>|<span data-ttu-id="f7e36-112">`celt` Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="f7e36-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="f7e36-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f7e36-113">S_FALSE</span></span>|<span data-ttu-id="f7e36-114">Weniger als `celt` Elemente wurden übersprungen, was darauf hinweist, dass keine weiteren Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f7e36-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7e36-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7e36-115">Remarks</span></span>  

 <span data-ttu-id="f7e36-116">Die neue Position des Cursors dieses Enumerators ist (aktuelle Position) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="f7e36-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7e36-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f7e36-117">Requirements</span></span>  

 <span data-ttu-id="f7e36-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7e36-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7e36-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7e36-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7e36-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7e36-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7e36-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7e36-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e36-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7e36-122">See also</span></span>

- [<span data-ttu-id="f7e36-123">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7e36-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="f7e36-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f7e36-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
