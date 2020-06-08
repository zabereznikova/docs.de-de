---
title: ICorProfilerCallback3::ProfilerDetachSucceeded-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type:
- apiref
ms.openlocfilehash: 93406dddf7babd8cf61032666737b993c2f721f4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499596"
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="30f92-102">ICorProfilerCallback3::ProfilerDetachSucceeded-Methode</span><span class="sxs-lookup"><span data-stu-id="30f92-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="30f92-103">Benachrichtigt den Profiler, dass die CLR (Common Language Runtime) die Profiler-DLL entladen wird.</span><span class="sxs-lookup"><span data-stu-id="30f92-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30f92-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="30f92-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="30f92-105">Return Value</span></span>  
 <span data-ttu-id="30f92-106">Der Rückgabewert von diesem Rückruf wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="30f92-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30f92-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="30f92-107">Remarks</span></span>  
 <span data-ttu-id="30f92-108">Der `ProfilerDetachSucceeded`-Rückruf wird ausgegeben, nachdem alle Threads den Code des Profilers beendet haben.</span><span class="sxs-lookup"><span data-stu-id="30f92-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="30f92-109">Wenn diese Methode aufgerufen wird, sollte der Profiler alle abschließenden Aufgaben ausführen, die nicht für seinen Destruktor geeignet sind, z. B. das Benachrichtigen seiner Benutzeroberfläche oder Protokollierungskomponente.</span><span class="sxs-lookup"><span data-stu-id="30f92-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="30f92-110">Allerdings darf der Profiler keine Funktionen für Schnittstellen aufzurufen, die von der CLR während dieses Rückrufs bereitgestellt werden (z. b. [ICorProfilerInfo](icorprofilerinfo-interface.md) oder `IMetaData*` Schnittstellen).</span><span class="sxs-lookup"><span data-stu-id="30f92-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="30f92-111">Die CLR erstellt einen Eintrag im Windows-Anwendungsereignisprotokoll, um anzugeben, dass der Trennvorgang erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="30f92-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="30f92-112">Nachdem der Profiler von diesem Rückruf zurückkehrt, gibt die CLR das Profilerobjekt frei und entlädt die Profiler-DLL.</span><span class="sxs-lookup"><span data-stu-id="30f92-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="30f92-113">Daher darf der Profiler keine Aktionen ausführen, die bewirken, dass die Ausführung in der Profiler-DLL erfolgt, nachdem er von diesem Rückruf zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="30f92-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="30f92-114">Es darf z. B. keine Threads erstellen oder Timerrückrufe registrieren.</span><span class="sxs-lookup"><span data-stu-id="30f92-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f92-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="30f92-115">Requirements</span></span>  
 <span data-ttu-id="30f92-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30f92-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f92-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="30f92-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="30f92-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30f92-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30f92-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f92-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f92-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="30f92-120">See also</span></span>

- [<span data-ttu-id="30f92-121">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="30f92-121">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
- [<span data-ttu-id="30f92-122">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30f92-122">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="30f92-123">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="30f92-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="30f92-124">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="30f92-124">Profiling</span></span>](index.md)
