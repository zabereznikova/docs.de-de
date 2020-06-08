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
ms.openlocfilehash: 3725b73ab55f6e4dc789a1fde8d1224695a174d7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499934"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="fd1d9-102">ICorProfilerCallback::RemotingServerInvocationStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="fd1d9-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="fd1d9-103">Benachrichtigt den Profiler, dass der Prozess eine Methode als Reaktion auf eine Aufruf Anforderung für eine Remote Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="fd1d9-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd1d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd1d9-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="fd1d9-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fd1d9-105">Requirements</span></span>  
 <span data-ttu-id="fd1d9-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd1d9-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd1d9-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd1d9-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd1d9-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd1d9-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd1d9-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd1d9-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1d9-110">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="fd1d9-110">See also</span></span>

- [<span data-ttu-id="fd1d9-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd1d9-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
