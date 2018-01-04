---
title: ICorProfilerInfo::SetEventMask-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetEventMask
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetEventMask
helpviewer_keywords:
- ICorProfilerInfo::SetEventMask method [.NET Framework profiling]
- SetEventMask method [.NET Framework profiling]
ms.assetid: 44bc0f56-32fa-491e-a62d-52fc96d48125
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c6fe763103e7b8aaf6d501c653342a21bd513b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="993e9-102">ICorProfilerInfo::SetEventMask-Methode</span><span class="sxs-lookup"><span data-stu-id="993e9-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="993e9-103">Legt einen Wert fest, der die Ereignistypen angibt, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="993e9-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="993e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="993e9-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="993e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="993e9-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="993e9-106">[in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="993e9-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="993e9-107">Jedes Bit steuert eine andere Funktion, ein anderes Verhalten oder einen anderen Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="993e9-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="993e9-108">Die Bits werden in beschrieben die [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="993e9-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="993e9-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="993e9-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="993e9-110">Rufen Sie die [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode statt dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="993e9-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="993e9-111">Obwohl die `SetEventMask` Methode weiterhin unterstützt, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) stellt zusätzliche Funktionalität bereit.</span><span class="sxs-lookup"><span data-stu-id="993e9-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="993e9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="993e9-112">Requirements</span></span>  
 <span data-ttu-id="993e9-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="993e9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="993e9-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="993e9-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="993e9-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="993e9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="993e9-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="993e9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="993e9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="993e9-117">See Also</span></span>  
 [<span data-ttu-id="993e9-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="993e9-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="993e9-119">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="993e9-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
