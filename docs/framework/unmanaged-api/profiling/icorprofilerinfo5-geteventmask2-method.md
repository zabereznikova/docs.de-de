---
title: ICorProfilerInfo5::GetEventMask2-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: f3943eef969f777b40dc51c4900b190561f14887
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868394"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="db1c5-102">ICorProfilerInfo5::GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="db1c5-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="db1c5-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="db1c5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="db1c5-104">Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="db1c5-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="db1c5-105">Sie stellt Funktionen bereit, die nicht von der [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="db1c5-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1c5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="db1c5-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db1c5-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="db1c5-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="db1c5-108">[out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="db1c5-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="db1c5-109">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="db1c5-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="db1c5-110">Die Bits werden in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db1c5-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="db1c5-111">[out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="db1c5-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="db1c5-112">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="db1c5-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="db1c5-113">Die Bits werden in der [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db1c5-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db1c5-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db1c5-114">Remarks</span></span>  
 <span data-ttu-id="db1c5-115">Die Methode `GetEventMask2` wird verwendet um feststellen, welchen Rückruf der Profiler abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="db1c5-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="db1c5-116">In der Regel führen Sie eine logische OR-`pdwEventsLow` und `pdwEventsHigh` Werte sowie alle neuen Bits aus, die Sie festlegen möchten, und dann die [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="db1c5-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="db1c5-117">Diese Methode ist die empfohlene Alternative zur [GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="db1c5-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1c5-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db1c5-118">Requirements</span></span>  
 <span data-ttu-id="db1c5-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db1c5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db1c5-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db1c5-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db1c5-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db1c5-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db1c5-122">**.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db1c5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1c5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db1c5-123">See also</span></span>

- [<span data-ttu-id="db1c5-124">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db1c5-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="db1c5-125">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="db1c5-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
