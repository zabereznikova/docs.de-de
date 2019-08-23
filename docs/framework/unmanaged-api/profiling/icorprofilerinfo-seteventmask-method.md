---
title: ICorProfilerInfo::SetEventMask-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEventMask
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e11628f9c20160899f37e62472547eaa98ea60b8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962650"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="f8ae6-102">ICorProfilerInfo::SetEventMask-Methode</span><span class="sxs-lookup"><span data-stu-id="f8ae6-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="f8ae6-103">Legt einen Wert fest, der die Ereignistypen angibt, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="f8ae6-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ae6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8ae6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8ae6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8ae6-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="f8ae6-106">[in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="f8ae6-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="f8ae6-107">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="f8ae6-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="f8ae6-108">Die Bits werden in der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8ae6-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8ae6-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8ae6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8ae6-110">Anstelle dieser Methode sollte die [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) -Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f8ae6-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="f8ae6-111">Obwohl die `SetEventMask` -Methode weiterhin unterstützt wird, bietet [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) zusätzliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="f8ae6-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8ae6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8ae6-112">Requirements</span></span>  
 <span data-ttu-id="f8ae6-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8ae6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8ae6-114">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="f8ae6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8ae6-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8ae6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8ae6-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8ae6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ae6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8ae6-117">See also</span></span>

- [<span data-ttu-id="f8ae6-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8ae6-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="f8ae6-119">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="f8ae6-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
