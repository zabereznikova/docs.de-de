---
title: ICorProfilerCallback::AssemblyUnloadStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2631650b55ec440a39a3c1a2e0c911f8868fed75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="b7594-102">ICorProfilerCallback::AssemblyUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b7594-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="b7594-103">Benachrichtigt den Profiler, dass eine Assembly entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b7594-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7594-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7594-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7594-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7594-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="b7594-106">[in] Identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b7594-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7594-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7594-107">Remarks</span></span>  
 <span data-ttu-id="b7594-108">Der Wert der `assemblyId` gilt nicht für eine Anforderung Informationen nach der `AssemblyUnloadStarted` -Methode zurückkehrt – Dies ist der Profiler die letzte Möglichkeit zum Abrufen von Informationen für diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="b7594-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7594-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7594-109">Requirements</span></span>  
 <span data-ttu-id="b7594-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7594-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7594-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7594-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7594-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7594-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7594-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7594-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7594-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7594-114">See Also</span></span>  
 [<span data-ttu-id="b7594-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7594-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b7594-116">AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="b7594-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
