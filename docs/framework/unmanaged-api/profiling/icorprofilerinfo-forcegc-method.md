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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 208552dd94f587b9326280ad455ca2478ae4ac4d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780252"
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="42442-102">ICorProfilerInfo::ForceGC-Methode</span><span class="sxs-lookup"><span data-stu-id="42442-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="42442-103">Erzwingt eine Garbagecollection in der common Language Runtime (CLR) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="42442-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42442-104">Syntax</span></span>  
  
```cpp  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="42442-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42442-105">Remarks</span></span>  
 <span data-ttu-id="42442-106">Die `ForceGC` -Methode muss aufgerufen werden, nur von einem Thread, der nie verwalteten Code ausgeführt hat, und verfügt nicht über die Profilerrückrufe für seinen Stapel.</span><span class="sxs-lookup"><span data-stu-id="42442-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="42442-107">Die einfachste Implementierung ist die Erstellung von einem separaten Thread innerhalb des Profilers, der aufruft `ForceGC` signalisiert.</span><span class="sxs-lookup"><span data-stu-id="42442-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42442-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42442-108">Requirements</span></span>  
 <span data-ttu-id="42442-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42442-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42442-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42442-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42442-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42442-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42442-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42442-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42442-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42442-113">See also</span></span>

- [<span data-ttu-id="42442-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42442-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
