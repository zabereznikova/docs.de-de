---
title: ICorProfilerCallback::RemotingServerInvocationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationStarted
helpviewer_keywords:
- RemotingServerInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerInvocationStarted method [.NET Framework profiling]
ms.assetid: 86051a11-ad8e-4ace-9a11-ff0f982a5e11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 091851a5729d496fb030f5d09402f524ca712ae6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556547"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="4b932-102">ICorProfilerCallback::RemotingServerInvocationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="4b932-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="4b932-103">Benachrichtigt den Profiler, dass der Prozess eine Methode in der Antwort auf eine Remotemethode aufrufanforderung aufruft.</span><span class="sxs-lookup"><span data-stu-id="4b932-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b932-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b932-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4b932-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b932-105">Requirements</span></span>  
 <span data-ttu-id="4b932-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b932-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b932-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b932-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b932-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b932-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b932-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b932-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b932-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b932-110">See also</span></span>
- [<span data-ttu-id="4b932-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b932-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
