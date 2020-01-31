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
ms.openlocfilehash: b08a501f7d55fbb193afd8c297ca7725348dac76
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860926"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="2a1e9-102">ICorProfilerThreadEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="2a1e9-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="2a1e9-103">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="2a1e9-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a1e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a1e9-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a1e9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="2a1e9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2a1e9-106">in Die Anzahl der Elemente, die übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2a1e9-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a1e9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2a1e9-107">Return Value</span></span>  
 <span data-ttu-id="2a1e9-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2a1e9-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2a1e9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a1e9-109">HRESULT</span></span>|<span data-ttu-id="2a1e9-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a1e9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a1e9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a1e9-111">S_OK</span></span>|<span data-ttu-id="2a1e9-112">`celt` Elemente wurden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="2a1e9-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="2a1e9-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2a1e9-113">S_FALSE</span></span>|<span data-ttu-id="2a1e9-114">Weniger als `celt` Elemente übersprungen wurden, was darauf hinweist, dass keine weiteren Elemente vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2a1e9-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a1e9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a1e9-115">Remarks</span></span>  
 <span data-ttu-id="2a1e9-116">Die neue Position des Cursors dieses Enumerators ist (aktuelle Position) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="2a1e9-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a1e9-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a1e9-117">Requirements</span></span>  
 <span data-ttu-id="2a1e9-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a1e9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a1e9-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a1e9-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a1e9-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a1e9-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a1e9-121">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a1e9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1e9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a1e9-122">See also</span></span>

- [<span data-ttu-id="2a1e9-123">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a1e9-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="2a1e9-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2a1e9-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
