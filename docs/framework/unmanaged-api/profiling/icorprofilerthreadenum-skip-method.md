---
title: ICorProfilerThreadEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: 12b7b53c408388c21d7508f6591ead5ccf55936b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721178"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="3febc-102">ICorProfilerThreadEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="3febc-102">ICorProfilerThreadEnum::Skip Method</span></span>

<span data-ttu-id="3febc-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="3febc-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3febc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3febc-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3febc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3febc-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="3febc-106">in Die Anzahl der Elemente, die übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3febc-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3febc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3febc-107">Return Value</span></span>  

 <span data-ttu-id="3febc-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3febc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3febc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3febc-109">HRESULT</span></span>|<span data-ttu-id="3febc-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3febc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3febc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3febc-111">S_OK</span></span>|<span data-ttu-id="3febc-112">`celt` Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="3febc-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="3febc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3febc-113">S_FALSE</span></span>|<span data-ttu-id="3febc-114">Weniger als `celt` Elemente wurden übersprungen, was darauf hinweist, dass keine weiteren Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3febc-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3febc-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3febc-115">Remarks</span></span>  

 <span data-ttu-id="3febc-116">Die neue Position des Cursors dieses Enumerators ist (aktuelle Position) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="3febc-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3febc-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3febc-117">Requirements</span></span>  

 <span data-ttu-id="3febc-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3febc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3febc-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3febc-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3febc-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3febc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3febc-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3febc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3febc-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3febc-122">See also</span></span>

- [<span data-ttu-id="3febc-123">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3febc-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="3febc-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3febc-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
