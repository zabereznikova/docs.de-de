---
title: ICorProfilerInfo::ForceGC-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.ForceGC
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3a3389c6675e992c362e3e0a77dfbc97e142ef8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoforcegc-method"></a><span data-ttu-id="6a915-102">ICorProfilerInfo::ForceGC-Methode</span><span class="sxs-lookup"><span data-stu-id="6a915-102">ICorProfilerInfo::ForceGC Method</span></span>
<span data-ttu-id="6a915-103">Erzwingt eine Garbagecollection in der common Language Runtime (CLR) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a915-103">Forces garbage collection to occur within the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a915-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a915-104">Syntax</span></span>  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6a915-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a915-105">Remarks</span></span>  
 <span data-ttu-id="6a915-106">Die `ForceGC` -Methode muss nur von einem Thread, die verwalteten Code wurde nie ausgeführt und verfügt nicht über die Profilerrückrufe für einen Stapel aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6a915-106">The `ForceGC` method must be called only from a thread that has never run managed code and does not have any profiler callbacks on its stack.</span></span> <span data-ttu-id="6a915-107">Die einfachste Implementierung ist auf einen separaten Thread innerhalb des Profilers zu erstellen, die aufruft `ForceGC` signalisiert.</span><span class="sxs-lookup"><span data-stu-id="6a915-107">The most convenient implementation is to create a separate thread within the profiler that calls `ForceGC` when signaled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a915-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a915-108">Requirements</span></span>  
 <span data-ttu-id="6a915-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a915-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a915-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a915-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a915-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a915-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a915-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a915-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a915-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a915-113">See Also</span></span>  
 [<span data-ttu-id="6a915-114">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a915-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
