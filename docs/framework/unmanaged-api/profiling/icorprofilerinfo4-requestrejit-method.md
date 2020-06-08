---
title: ICorProfilerInfo4::RequestReJIT-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
ms.openlocfilehash: 7dd82f2dfab885070df4789fe5efc16a49d50e06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495800"
---
# <a name="icorprofilerinfo4requestrejit-method"></a><span data-ttu-id="1fb31-102">ICorProfilerInfo4::RequestReJIT-Methode</span><span class="sxs-lookup"><span data-stu-id="1fb31-102">ICorProfilerInfo4::RequestReJIT Method</span></span>
<span data-ttu-id="1fb31-103">Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="1fb31-103">Requests a JIT recompilation of all instances of the specified functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fb31-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fb31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1fb31-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="1fb31-106">[in] Die Anzahl der neu zu kompilierenden Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1fb31-106">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="1fb31-107">[in] Gibt den `moduleId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="1fb31-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="1fb31-108">[in] Gibt den `methodId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die neu zu kompilierenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="1fb31-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fb31-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1fb31-109">Return Value</span></span>  
 <span data-ttu-id="1fb31-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1fb31-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1fb31-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1fb31-111">HRESULT</span></span>|<span data-ttu-id="1fb31-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1fb31-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1fb31-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fb31-113">S_OK</span></span>|<span data-ttu-id="1fb31-114">Es wurde versucht, alle Methoden für die JIT-Neukompilierung zu markieren.</span><span class="sxs-lookup"><span data-stu-id="1fb31-114">An attempt was made to mark all the methods for JIT recompilation.</span></span> <span data-ttu-id="1fb31-115">Der Profiler muss die [ICorProfilerCallback4:: rejiterror](icorprofilercallback4-rejiterror-method.md) -Methode implementieren, um zu bestimmen, welche Methoden erfolgreich für die JIT-Neukompilierung gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="1fb31-115">The profiler must implement the [ICorProfilerCallback4::ReJITError](icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.</span></span>|  
|<span data-ttu-id="1fb31-116">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="1fb31-116">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="1fb31-117">Der Profiler muss die [ICorProfilerCallback4](icorprofilercallback4-interface.md) -Schnittstelle implementieren, damit dieser-Befehl unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1fb31-117">The profiler must implement the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="1fb31-118">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="1fb31-118">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="1fb31-119">Die JIT-Neukompilierung wurde nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1fb31-119">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="1fb31-120">Sie müssen die JIT-Neukompilierung während der Initialisierung aktivieren, indem Sie die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um das-Flag festzulegen `COR_PRF_ENABLE_REJIT` .</span><span class="sxs-lookup"><span data-stu-id="1fb31-120">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="1fb31-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1fb31-121">E_INVALIDARG</span></span>|<span data-ttu-id="1fb31-122">`cFunctions` ist 0, oder `moduleIds` oder `methodIds` ist `NULL`.</span><span class="sxs-lookup"><span data-stu-id="1fb31-122">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|||  
|<span data-ttu-id="1fb31-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1fb31-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1fb31-124">Die CLR konnte die Anforderung nicht abschließen, da nicht genügend Arbeitsspeicher vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="1fb31-124">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fb31-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1fb31-125">Remarks</span></span>  
 <span data-ttu-id="1fb31-126">Rufen Sie `RequestReJIT` auf, damit die Common Language Runtime einen angegebenen Satz von Funktionen neu kompiliert.</span><span class="sxs-lookup"><span data-stu-id="1fb31-126">Call `RequestReJIT` to have the runtime recompile a specified set of functions.</span></span> <span data-ttu-id="1fb31-127">Ein Codeprofiler kann dann die [icorprofilerfunctioncontrol](icorprofilerfunctioncontrol-interface.md) -Schnittstelle verwenden, um den Code anzupassen, der generiert wird, wenn die Funktionen erneut kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="1fb31-127">A code profiler can then use the [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled.</span></span> <span data-ttu-id="1fb31-128">Dies wirkt sich nicht auf derzeit ausgeführte Funktionen, sondern nur auf zukünftige Funktionsaufrufe aus.</span><span class="sxs-lookup"><span data-stu-id="1fb31-128">This does not affect currently executing functions, only future function invocations.</span></span> <span data-ttu-id="1fb31-129">Wenn eine der angegebenen Funktionen bereits zuvor erneut JIT-kompiliert wurde, entspricht das Anfordern einer Neukompilierung dem Zurücksetzen und erneuten Kompilieren der Funktion.</span><span class="sxs-lookup"><span data-stu-id="1fb31-129">If any of the specified functions has previously been JIT-recompiled, requesting a recompilation is equivalent to reverting and recompiling the function.</span></span> <span data-ttu-id="1fb31-130">Um die Umkehrbarkeit zu bewahren, berücksichtigt der JIT-Compiler beim Kompilieren der ursprünglichen Version einer Funktion nur die ursprünglichen Versionen der Aufgerufenen bei Entscheidungen zum Inlining.</span><span class="sxs-lookup"><span data-stu-id="1fb31-130">To preserve reversibility, when the JIT compiler compiles the original version of a function, it considers only the original versions of its callees for inlining decisions.</span></span> <span data-ttu-id="1fb31-131">Wenn der JIT-Compiler eine Funktion neu kompiliert, berücksichtigt er die aktuellen Versionen (erneut kompilierte oder ursprüngliche Versionen) der Aufgerufenen für das Inlining.</span><span class="sxs-lookup"><span data-stu-id="1fb31-131">When the JIT compiler recompiles a function, it considers the current versions (recompiled or original) of its callees for inlining.</span></span>  
  
 <span data-ttu-id="1fb31-132">Ein Profiler ruft in der Regel `RequestReJIT` als Reaktion auf eine Benutzereingabe auf, mit der angefordert wird, dass der Profiler eine oder mehrere Methoden instrumentiert.</span><span class="sxs-lookup"><span data-stu-id="1fb31-132">A profiler typically calls `RequestReJIT` in response to user input requesting that the profiler instrument one or more methods.</span></span> <span data-ttu-id="1fb31-133">`RequestReJIT` hält normalerweise die Common Language Runtime an, um einige Aufgaben auszuführen, und kann möglicherweise eine Garbage Collection auslösen.</span><span class="sxs-lookup"><span data-stu-id="1fb31-133">`RequestReJIT` typically suspends the runtime in order to do some of its work, and can potentially trigger a garbage collection.</span></span> <span data-ttu-id="1fb31-134">Daher sollte der Profiler `RequestReJIT` aus einem zuvor erstellten Thread aufrufen und nicht aus einem durch die CLR erstellten Thread, der aktuell einen Profilerrückruf ausführt.</span><span class="sxs-lookup"><span data-stu-id="1fb31-134">As such, the profiler should call `RequestReJIT` from a thread it previously created, and not from a CLR-created thread that is currently executing a profiler callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fb31-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1fb31-135">Requirements</span></span>  
 <span data-ttu-id="1fb31-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fb31-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fb31-137">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fb31-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1fb31-138">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fb31-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fb31-139">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb31-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb31-140">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="1fb31-140">See also</span></span>

- [<span data-ttu-id="1fb31-141">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1fb31-141">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="1fb31-142">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1fb31-142">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1fb31-143">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="1fb31-143">Profiling</span></span>](index.md)
