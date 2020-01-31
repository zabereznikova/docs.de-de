---
title: ICorProfilerCallback::ThreadAssignedToOSThread-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 0e8c91f65d4ebec07689a42d4517fc100fce136d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865843"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="1fa3a-102">ICorProfilerCallback::ThreadAssignedToOSThread-Methode</span><span class="sxs-lookup"><span data-stu-id="1fa3a-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="1fa3a-103">Benachrichtigt den Profiler, dass ein verwalteter Thread mithilfe eines bestimmten Betriebssystem Threads implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fa3a-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fa3a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1fa3a-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="1fa3a-106">in Der Bezeichner des verwalteten Threads.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="1fa3a-107">in Der Bezeichner des Betriebssystem Threads.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fa3a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1fa3a-108">Remarks</span></span>  
 <span data-ttu-id="1fa3a-109">Der `ThreadAssignedToOSThread` Rückruf ist vorhanden, sodass der Profiler eine genaue Zuordnung zwischen Fibers von Betriebssystemthreads und verwalteten Threads aufrechterhalten kann.</span><span class="sxs-lookup"><span data-stu-id="1fa3a-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fa3a-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1fa3a-110">Requirements</span></span>  
 <span data-ttu-id="1fa3a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fa3a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fa3a-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fa3a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1fa3a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fa3a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fa3a-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fa3a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa3a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fa3a-115">See also</span></span>

- [<span data-ttu-id="1fa3a-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1fa3a-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
