---
title: ICorProfilerInfo::ForceGC-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
ms.openlocfilehash: e1fe38419cda328c919f0840d51cf6336919aa60
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864192"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="2d7cc-102">ICorProfilerInfo::ForceGC-Methode</span><span class="sxs-lookup"><span data-stu-id="2d7cc-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="2d7cc-103">Erzwingt, dass Garbage Collection im Common Language Runtime (CLR) auftritt.</span><span class="sxs-lookup"><span data-stu-id="2d7cc-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d7cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d7cc-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2d7cc-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d7cc-105">Remarks</span></span>  
 <span data-ttu-id="2d7cc-106">Die `ForceGC`-Methode muss nur von einem Thread aufgerufen werden, der niemals verwalteten Code ausgeführt hat und über keine Profiler-Rückrufe auf dem Stapel verfügt.</span><span class="sxs-lookup"><span data-stu-id="2d7cc-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="2d7cc-107">Die am einfachsten geeignete Implementierung besteht darin, einen separaten Thread innerhalb des Profilers zu erstellen, der `ForceGC` bei Signalisierung aufruft.</span><span class="sxs-lookup"><span data-stu-id="2d7cc-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d7cc-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d7cc-108">Requirements</span></span>  
 <span data-ttu-id="2d7cc-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d7cc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d7cc-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d7cc-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d7cc-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d7cc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d7cc-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d7cc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d7cc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d7cc-113">See also</span></span>

- [<span data-ttu-id="2d7cc-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d7cc-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
