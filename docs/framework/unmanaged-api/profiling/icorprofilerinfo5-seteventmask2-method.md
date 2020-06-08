---
title: ICorProfilerInfo5::SetEventMask2-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 8027cdcde8281c363207e309bf65fcd90c03b626
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495618"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="9c113-102">ICorProfilerInfo5::SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="9c113-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="9c113-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="9c113-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="9c113-104">Legt einen Wert fest, der die Ereignistypen angibt, für die der Profiler Ereignisbenachrichtigungen von der Common Language Runtime (CLR) erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="9c113-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="9c113-105">Sie bietet mehr Funktionen als die [ICorProfilerInfo:: Log Test](icorprofilerinfo-seteventmask-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="9c113-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c113-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c113-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c113-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c113-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="9c113-108">[in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="9c113-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="9c113-109">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="9c113-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="9c113-110">Die Bits werden in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c113-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="9c113-111">[in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="9c113-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="9c113-112">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="9c113-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="9c113-113">Die Bits werden in der [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c113-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c113-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9c113-114">Remarks</span></span>  
 <span data-ttu-id="9c113-115">Die `SetEventMask2`-Methode wird verwendet, um die Rückrufe festzulegen, die der Profiler abonniert.</span><span class="sxs-lookup"><span data-stu-id="9c113-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="9c113-116">In der Regel wird die [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) -Methode aufgerufen, um zu bestimmen, welche Bits festgelegt sind, wie Sie die `pdwEventsLow` `pdwEventsHigh` Werte und und alle neuen Bits, die Sie festlegen möchten, durchführen und dann die- `SetEventMask2` Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="9c113-116">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="9c113-117">Diese Methode ist die empfohlene Alternative zur Methode " [" der Methode](icorprofilerinfo-seteventmask-method.md) "" von "".</span><span class="sxs-lookup"><span data-stu-id="9c113-117">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c113-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9c113-118">Requirements</span></span>  
 <span data-ttu-id="9c113-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c113-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c113-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9c113-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c113-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c113-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c113-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c113-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c113-123">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="9c113-123">See also</span></span>

- [<span data-ttu-id="9c113-124">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c113-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="9c113-125">GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="9c113-125">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
