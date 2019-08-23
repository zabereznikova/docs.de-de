---
title: ICorProfilerInfo::GetEventMask-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetEventMask
helpviewer_keywords:
- GetEventMask method [.NET Framework profiling]
- ICorProfilerInfo::GetEventMask method [.NET Framework profiling]
ms.assetid: ec34cc13-45a3-4695-abc3-b3347d4e6fc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fea50b9d42511540197c80d4ba402834b216830
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957948"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="b4663-102">ICorProfilerInfo::GetEventMask-Methode</span><span class="sxs-lookup"><span data-stu-id="b4663-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="b4663-103">Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Ereignisbenachrichtigungen von der Common Language Runtime (CLR) erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="b4663-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4663-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4663-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4663-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4663-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="b4663-106">[out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="b4663-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="b4663-107">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="b4663-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="b4663-108">Die Bits werden in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4663-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4663-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4663-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4663-110">Anstelle dieser Methode sollte die [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) -Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b4663-110">You should call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="b4663-111">Obwohl die `SetEventMask` -Methode weiterhin unterstützt wird, bietet [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) zusätzliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b4663-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4663-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4663-112">Requirements</span></span>  
 <span data-ttu-id="b4663-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4663-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4663-114">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="b4663-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4663-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4663-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4663-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4663-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4663-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4663-117">See also</span></span>

- [<span data-ttu-id="b4663-118">GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="b4663-118">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="b4663-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4663-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
