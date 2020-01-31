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
ms.openlocfilehash: 63f19fe899abd75380249e171f248480949bc471
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863906"
---
# <a name="icorprofilerinfogeteventmask-method"></a><span data-ttu-id="18526-102">ICorProfilerInfo::GetEventMask-Methode</span><span class="sxs-lookup"><span data-stu-id="18526-102">ICorProfilerInfo::GetEventMask Method</span></span>
<span data-ttu-id="18526-103">Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Ereignisbenachrichtigungen von der Common Language Runtime (CLR) erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="18526-103">Gets the current event categories for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18526-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18526-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventMask(  
    [out] DWORD *pdwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18526-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="18526-105">Parameters</span></span>  
 `pdwEvents`  
 <span data-ttu-id="18526-106">[out] Ein Zeiger auf einen 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="18526-106">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="18526-107">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="18526-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="18526-108">Die Bits werden in der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="18526-108">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18526-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18526-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18526-110">Anstelle dieser Methode sollte die [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) -Methode aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="18526-110">You should call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="18526-111">Obwohl die `SetEventMask`-Methode weiterhin unterstützt wird, bietet [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) zusätzliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="18526-111">Although the `SetEventMask` method continues to be supported, [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18526-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18526-112">Requirements</span></span>  
 <span data-ttu-id="18526-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18526-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18526-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18526-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18526-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18526-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18526-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18526-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18526-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18526-117">See also</span></span>

- [<span data-ttu-id="18526-118">GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="18526-118">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
- [<span data-ttu-id="18526-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18526-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
