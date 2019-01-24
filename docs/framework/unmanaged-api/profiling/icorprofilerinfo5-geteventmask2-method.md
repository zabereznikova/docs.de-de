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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 467be5a02b2e202b2e0e4f6a36b748ab6e0e8dbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731217"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="dbb80-102">ICorProfilerInfo5::GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="dbb80-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="dbb80-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="dbb80-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dbb80-104">Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="dbb80-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="dbb80-105">Es bietet Funktionalität, die nicht von der [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="dbb80-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb80-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbb80-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbb80-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbb80-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="dbb80-108">[out] Ein Zeiger zu einem 4-Byte-Wert, der die Kategorien des Ereignisses festlegt.</span><span class="sxs-lookup"><span data-stu-id="dbb80-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="dbb80-109">Jedes Bit steuert eine andere Funktion, ein anderes Verhalten oder einen anderen Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="dbb80-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="dbb80-110">Die Bits werden beschrieben, der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dbb80-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="dbb80-111">[out] Ein Zeiger zu einem 4-Byte-Wert, der die Kategorien des Ereignisses festlegt.</span><span class="sxs-lookup"><span data-stu-id="dbb80-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="dbb80-112">Jedes Bit steuert eine andere Funktion, ein anderes Verhalten oder einen anderen Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="dbb80-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="dbb80-113">Die Bits werden beschrieben, der [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="dbb80-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbb80-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbb80-114">Remarks</span></span>  
 <span data-ttu-id="dbb80-115">Die Methode `GetEventMask2` wird verwendet um feststellen, welchen Rückruf der Profiler abonniert hat.</span><span class="sxs-lookup"><span data-stu-id="dbb80-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="dbb80-116">In der Regel ein logisches OR der Durchführung der `pdwEventsLow` und `pdwEventsHigh` Werte sowie neuer Bits festgelegt, und klicken Sie dann aufgerufen werden soll die [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="dbb80-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="dbb80-117">Diese Methode ist die empfohlene Alternative zur der [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="dbb80-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb80-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbb80-118">Requirements</span></span>  
 <span data-ttu-id="dbb80-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbb80-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb80-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dbb80-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dbb80-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbb80-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbb80-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbb80-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb80-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbb80-123">See also</span></span>
- [<span data-ttu-id="dbb80-124">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbb80-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="dbb80-125">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="dbb80-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
