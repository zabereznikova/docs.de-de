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
ms.openlocfilehash: 122a621552b49f476f219216ac0a52011c1542ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860944"
---
# <a name="icorprofilerinfoseteventmask-method"></a><span data-ttu-id="004e7-102">ICorProfilerInfo::SetEventMask-Methode</span><span class="sxs-lookup"><span data-stu-id="004e7-102">ICorProfilerInfo::SetEventMask Method</span></span>
<span data-ttu-id="004e7-103">Legt einen Wert fest, der die Ereignistypen angibt, für die der Profiler Benachrichtigungen von der Common Language Runtime (CLR) erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="004e7-103">Sets a value that specifies the types of events for which the profiler wants to receive notification from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="004e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="004e7-104">Syntax</span></span>  
  
```  
HRESULT SetEventMask(  
    [in] DWORD dwEvents);  
```  
  
## <a name="parameters"></a><span data-ttu-id="004e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="004e7-105">Parameters</span></span>  
 `dwEvents`  
 <span data-ttu-id="004e7-106">[in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="004e7-106">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="004e7-107">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="004e7-107">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="004e7-108">Die Bits werden beschrieben, der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="004e7-108">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="004e7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="004e7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="004e7-110">Rufen Sie die [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) Methode statt dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="004e7-110">You should call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method instead of this method.</span></span> <span data-ttu-id="004e7-111">Obwohl die `SetEventMask` Methode weiterhin unterstützt, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) bietet zusätzliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="004e7-111">Although the `SetEventMask` method continues to be supported, [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) provides additional functionality.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="004e7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="004e7-112">Requirements</span></span>  
 <span data-ttu-id="004e7-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="004e7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="004e7-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="004e7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="004e7-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="004e7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="004e7-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="004e7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004e7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="004e7-117">See also</span></span>

- [<span data-ttu-id="004e7-118">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="004e7-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="004e7-119">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="004e7-119">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
