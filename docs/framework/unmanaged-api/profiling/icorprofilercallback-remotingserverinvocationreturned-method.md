---
title: ICorProfilerCallback::RemotingServerInvocationReturned-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3f32b9ab9b4e29dd101729dc43cde03985f5994
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451223"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="732b8-102">ICorProfilerCallback::RemotingServerInvocationReturned-Methode</span><span class="sxs-lookup"><span data-stu-id="732b8-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="732b8-103">Benachrichtigt den Profiler, dass das Aufrufen einer Methode als Reaktion auf eine Remotemethode Aufruf-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="732b8-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="732b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="732b8-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="732b8-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="732b8-105">Requirements</span></span>  
 <span data-ttu-id="732b8-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="732b8-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="732b8-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="732b8-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="732b8-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="732b8-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="732b8-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="732b8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="732b8-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="732b8-110">See Also</span></span>  
 [<span data-ttu-id="732b8-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="732b8-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
