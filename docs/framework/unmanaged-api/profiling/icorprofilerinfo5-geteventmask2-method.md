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
ms.openlocfilehash: 81509db178b0ab1a524dcc4b00f39264e87a220d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682782"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="81124-102">ICorProfilerInfo5::GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="81124-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>

<span data-ttu-id="81124-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="81124-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="81124-104">Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="81124-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="81124-105">Sie stellt Funktionen bereit, die nicht von der [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="81124-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81124-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="81124-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81124-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="81124-107">Parameters</span></span>  

 `pdwEventsLow`  
 <span data-ttu-id="81124-108">[out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="81124-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="81124-109">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="81124-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="81124-110">Die Bits werden in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="81124-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="81124-111">[out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="81124-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="81124-112">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="81124-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="81124-113">Die Bits werden in der [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="81124-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81124-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81124-114">Remarks</span></span>  

 <span data-ttu-id="81124-115">Die Methode `GetEventMask2` wird verwendet um feststellen, welchen Rückruf der Profiler abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="81124-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="81124-116">Normalerweise führen Sie ein logisches OR der `pdwEventsLow` Werte und `pdwEventsHigh` und neuer Bits aus, die Sie festlegen möchten, und dann die [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="81124-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="81124-117">Diese Methode ist die empfohlene Alternative zur [GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="81124-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81124-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="81124-118">Requirements</span></span>  

 <span data-ttu-id="81124-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81124-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81124-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81124-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81124-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81124-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81124-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81124-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81124-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81124-123">See also</span></span>

- [<span data-ttu-id="81124-124">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81124-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="81124-125">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="81124-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
