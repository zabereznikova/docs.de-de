---
title: ICorProfilerInfo2::DoStackSnapshot-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
ms.openlocfilehash: 10cc9dedfa34cd5235df721d7010bbd928fbc3ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727236"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="3bb5a-102">ICorProfilerInfo2::DoStackSnapshot-Methode</span><span class="sxs-lookup"><span data-stu-id="3bb5a-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>

<span data-ttu-id="3bb5a-103">Führt die verwalteten Frames auf dem Stapel für den angegebenen Thread durch und sendet Informationen über einen Rückruf an den Profiler.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bb5a-104">Syntax</span></span>  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bb5a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3bb5a-105">Parameters</span></span>  

 `thread`  
 <span data-ttu-id="3bb5a-106">in Die ID des Ziel Threads.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="3bb5a-107">Wenn NULL in übergeben wird, wird `thread` eine Momentaufnahme des aktuellen Threads erstellt.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="3bb5a-108">Wenn eine `ThreadID` von einem anderen Thread übermittelt wird, hält der Common Language Runtime (CLR) diesen Thread an, führt die Momentaufnahme aus und nimmt den Wert wieder auf.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="3bb5a-109">in Ein Zeiger auf die Implementierung der [StackSnapshotCallback](stacksnapshotcallback-function.md) -Methode, die von der CLR aufgerufen wird, um dem Profiler Informationen über jeden verwalteten Frame und jede Ausführung nicht verwalteter Frames bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-109">[in] A pointer to the implementation of the [StackSnapshotCallback](stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="3bb5a-110">Die- `StackSnapshotCallback` Methode wird vom Profiler-Writer implementiert.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="3bb5a-111">in Ein Wert der [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) -Enumeration, die die Menge der Daten angibt, die für jeden Frame von zurückgegeben werden sollen `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="3bb5a-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="3bb5a-112">in Ein Zeiger auf die Client Daten, die direkt an die Rückruffunktion übermittelt werden `StackSnapshotCallback` .</span><span class="sxs-lookup"><span data-stu-id="3bb5a-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="3bb5a-113">in Ein Zeiger auf eine Win32-- `CONTEXT` Struktur, die verwendet wird, um den Stapel Durchlauf zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="3bb5a-114">Die Win32 `CONTEXT` -Struktur enthält Werte der CPU-Register und stellt den Status der CPU zu einem bestimmten Zeitpunkt dar.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="3bb5a-115">Der Seed unterstützt die CLR dabei, zu bestimmen, wo der Stapel Durchlauf begonnen werden soll, wenn der obere Rand des Stapels nicht verwalteten Hilfscode ist. Andernfalls wird der Seed ignoriert.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="3bb5a-116">Für einen asynchronen Durchlauf muss ein Ausgangswerten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="3bb5a-117">Wenn Sie eine synchrone Exemplarische Vorgehensweise durchführen, ist kein Ausgangswert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="3bb5a-118">Der- `context` Parameter ist nur gültig, wenn das COR_PRF_SNAPSHOT_CONTEXT-Flag im-Parameter übergeben wurde `infoFlags` .</span><span class="sxs-lookup"><span data-stu-id="3bb5a-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3bb5a-119">in Die Größe der- `CONTEXT` Struktur, auf die vom-Parameter verwiesen wird `context` .</span><span class="sxs-lookup"><span data-stu-id="3bb5a-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bb5a-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bb5a-120">Remarks</span></span>  

 <span data-ttu-id="3bb5a-121">Durch die Übergabe von NULL für wird `thread` eine Momentaufnahme des aktuellen Threads erstellt.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="3bb5a-122">Momentaufnahmen können nur von anderen Threads übernommen werden, wenn der Zielthread zu diesem Zeitpunkt angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="3bb5a-123">Wenn der Profiler den Stapel durchlaufen möchte, wird aufgerufen `DoStackSnapshot` .</span><span class="sxs-lookup"><span data-stu-id="3bb5a-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="3bb5a-124">Bevor die CLR von diesem Aufruf zurückkehrt, ruft Sie `StackSnapshotCallback` mehrmals auf, und zwar für jeden verwalteten Frame (bzw. durch Ausführen von nicht verwalteten Frames) auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="3bb5a-125">Wenn nicht verwaltete Frames gefunden werden, müssen Sie Sie selbst durchgehen.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="3bb5a-126">Die Reihenfolge, in der der Stapel durchlaufen wird, ist das Gegenteil, wie die Frames auf den Stapel verschoben werden: Blatt (zuletzt per pushübertragung), erster Hauptrahmen (First-pushübertragung).</span><span class="sxs-lookup"><span data-stu-id="3bb5a-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="3bb5a-127">Weitere Informationen zum Programmieren des Profilers zum Durchlaufen verwalteter Stapel finden Sie unter [Profiler Stack Walking in the .NET Framework 2,0: Basics and Beyond](/previous-versions/dotnet/articles/bb264782(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="3bb5a-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](/previous-versions/dotnet/articles/bb264782(v=msdn.10)).</span></span>  
  
 <span data-ttu-id="3bb5a-128">Ein Stackwalk kann synchron oder asynchron sein, wie in den folgenden Abschnitten erläutert.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="3bb5a-129">Synchroner Stackwalk</span><span class="sxs-lookup"><span data-stu-id="3bb5a-129">Synchronous Stack Walk</span></span>  

 <span data-ttu-id="3bb5a-130">Ein synchroner Stackwalk umfasst das Durchlaufen des Stapels des aktuellen Threads als Reaktion auf einen Rückruf.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="3bb5a-131">Das Seeding oder das Anhalten ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="3bb5a-132">Sie führen einen synchronen Aufruf aus, wenn Sie als Antwort auf die CLR, die eine der [ICorProfilerCallback](icorprofilercallback-interface.md) (oder [ICorProfilerCallback2](icorprofilercallback2-interface.md))-Methoden Ihres Profilers aufruft, aufrufen, `DoStackSnapshot` um den Stapel des aktuellen Threads zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](icorprofilercallback-interface.md) (or [ICorProfilerCallback2](icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="3bb5a-133">Dies ist hilfreich, wenn Sie sehen möchten, wie der Stapel in einer Benachrichtigung wie z. b. [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md)aussieht.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="3bb5a-134">Sie können nur in `DoStackSnapshot` `ICorProfilerCallback` der-Methode aufzurufen und dabei NULL im `context` -Parameter und im- `thread` Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="3bb5a-135">Asynchroner Stackwalk</span><span class="sxs-lookup"><span data-stu-id="3bb5a-135">Asynchronous Stack Walk</span></span>  

 <span data-ttu-id="3bb5a-136">Ein asynchroner Stapel Durchlauf umfasst das Durchlaufen des Stapels eines anderen Threads oder das Durchlaufen des Stapels des aktuellen Threads, nicht als Reaktion auf einen Rückruf, sondern durch das Hijacking des Anweisungs Zeigers des aktuellen Threads.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="3bb5a-137">Ein asynchroner Durchlauf erfordert einen Ausgangswert, wenn der obere Rand des Stapels nicht verwalteter Code ist, der nicht Teil eines Platt Form Aufrufs (PInvoke) oder com-Aufrufs ist, sondern Hilfscode in der CLR selbst ist.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="3bb5a-138">Beispielsweise ist Code, der Just-in-time (JIT)-Kompilierung oder-Garbage Collection durchführt, Hilfscode.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="3bb5a-139">Sie erhalten einen Ausgangswert, indem Sie den Zielthread direkt anhalten und den Stapel selbst durchlaufen, bis Sie den obersten verwalteten Frame gefunden haben.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="3bb5a-140">Nachdem der Zielthread angehalten wurde, wird der aktuelle Registrierungs Kontext des Zielthreads angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="3bb5a-141">Legen Sie als nächstes fest, ob der Registrierungs Kontext auf nicht verwalteten Code zeigt, indem Sie [ICorProfilerInfo:: GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md) – aufrufen, wenn ein `FunctionID` gleich NULL zurückgegeben wird, der Frame nicht verwalteter Code ist.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="3bb5a-142">Durchlaufen Sie nun den Stapel, bis Sie den ersten verwalteten Frame erreichen, und berechnen Sie dann den Seed-Kontext basierend auf dem Registrierungs Kontext für diesen Frame.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="3bb5a-143">Greifen `DoStackSnapshot` Sie mit Ihrem Seed-Kontext zu, um den asynchronen Stapel Durchlauf zu starten.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="3bb5a-144">Wenn Sie keinen Ausgangs Ausgangsbereich angeben, `DoStackSnapshot` überspringt möglicherweise verwaltete Frames am oberen Rand des Stapels und gibt somit einen unvollständigen Stapel Durchlauf aus.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="3bb5a-145">Wenn Sie einen Ausgangswert angeben, muss er auf JIT-kompilierten oder von System eigenem Image Generator (Ngen.exe) generierten Code verweisen. Andernfalls wird `DoStackSnapshot` der Fehlercode zurückgegeben, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="3bb5a-146">Asynchrone Stapel Durchgänge können auf einfache Weise Deadlocks oder Zugriffs Verletzungen verursachen, es sei denn, Sie befolgen die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="3bb5a-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
- <span data-ttu-id="3bb5a-147">Wenn Sie Threads direkt aussetzen, denken Sie daran, dass nur ein Thread, der verwalteten Code nie ausgeführt hat, einen anderen Thread unterbrechen kann.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
- <span data-ttu-id="3bb5a-148">Blockieren Sie in Ihrem [ICorProfilerCallback:: Thread}](icorprofilercallback-threaddestroyed-method.md) -Rückruf immer, bis der Stapel Durchlauf dieses Threads beendet ist.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
- <span data-ttu-id="3bb5a-149">Behalten Sie keine Sperre bei, während der Profiler eine CLR-Funktion aufruft, die eine Garbage Collection auslöst.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="3bb5a-150">Das heißt, keine Sperre aufrechterhalten, wenn der besitzende Thread einen-Garbage Collection auslösen kann, der einen auslöst.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="3bb5a-151">Außerdem besteht das Risiko eines Deadlocks, wenn Sie `DoStackSnapshot` von einem Thread aufgerufen werden, den Ihr Profiler erstellt hat, sodass Sie den Stapel eines separaten Zielthreads durchlaufen können.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="3bb5a-152">Beim ersten Mal, wenn der von Ihnen erstellte Thread bestimmte `ICorProfilerInfo*` Methoden (einschließlich) eingibt `DoStackSnapshot` , führt die CLR die Thread spezifische Initialisierung pro Thread in diesem Thread aus.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="3bb5a-153">Wenn Ihr Profiler den Zielthread angehalten hat, dessen Stapel Sie durchlaufen möchten, und wenn der Zielthread eine Sperre besitzt, die für die Durchführung dieser Thread spezifischen Initialisierung erforderlich ist, tritt ein Deadlock auf.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="3bb5a-154">Um diesen Deadlock zu vermeiden, führen Sie einen ersten Rückruf `DoStackSnapshot` von aus dem vom Profiler erstellten Thread aus, um einen separaten Zielthread zu durchlaufen, aber halten Sie den Zielthread nicht an erster Stelle.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="3bb5a-155">Dieser anfängliche-Befehl stellt sicher, dass die Initialisierung pro Thread ohne deadlockvorgang durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="3bb5a-156">Wenn `DoStackSnapshot` erfolgreich ist und mindestens einen Frame meldet, ist es nach diesem Punkt sicher, dass der vom Profiler erstellte Thread sicher ist, dass ein beliebiger Zielthread angehalten und aufgerufen wird, `DoStackSnapshot` um den Stapel dieses Zielthreads zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb5a-157">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3bb5a-157">Requirements</span></span>  

 <span data-ttu-id="3bb5a-158">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bb5a-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb5a-159">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3bb5a-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3bb5a-160">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bb5a-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bb5a-161">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb5a-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb5a-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3bb5a-162">See also</span></span>

- [<span data-ttu-id="3bb5a-163">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bb5a-163">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="3bb5a-164">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bb5a-164">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
