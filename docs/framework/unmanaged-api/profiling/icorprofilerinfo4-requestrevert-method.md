---
title: ICorProfilerInfo4::RequestRevert-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestRevert
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestRevert
helpviewer_keywords:
- RequestRevert method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestRevert method [.NET Framework profiling]
ms.assetid: 70261da5-5933-4e25-9de0-ddf51cba56cc
topic_type:
- apiref
ms.openlocfilehash: 73d122b1ffa890bfa43f8eef7e24595ac0d26ebe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861787"
---
# <a name="icorprofilerinfo4requestrevert-method"></a><span data-ttu-id="4afd7-102">ICorProfilerInfo4::RequestRevert-Methode</span><span class="sxs-lookup"><span data-stu-id="4afd7-102">ICorProfilerInfo4::RequestRevert Method</span></span>
<span data-ttu-id="4afd7-103">Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="4afd7-103">Reverts all instances of the specified functions to their original versions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4afd7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4afd7-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestRevert (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[],  
   [out, size_is(cFunctions)]  HRESULT status[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4afd7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4afd7-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="4afd7-106">[in] Die Anzahl der zurückzusetzenden Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4afd7-106">[in] The number of functions to revert.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="4afd7-107">[in] Gibt den `moduleId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die zurückzusetzenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4afd7-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="4afd7-108">[in] Gibt den `methodId`-Teil der (`module`, `methodDef`)-Paare an, mit denen die zurückzusetzenden Funktionen identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4afd7-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be reverted.</span></span>  
  
 `status`  
 <span data-ttu-id="4afd7-109">[out] Ein Array von HRESULTs, das im Abschnitt "Status HRESULTs" weiter unten in diesem Thema aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="4afd7-109">[out] An array of HRESULTs listed in the "Status HRESULTs" section later in this topic.</span></span> <span data-ttu-id="4afd7-110">Jedes HRESULT gibt das erfolgreiche oder fehlgeschlagene Zurücksetzen der einzelnen Funktionen an, die in den parallelen Arrays `moduleIds` und `methodIds` angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="4afd7-110">Each HRESULT indicates the success or failure of trying to revert each function specified in the parallel arrays `moduleIds` and `methodIds`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4afd7-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4afd7-111">Return Value</span></span>  
 <span data-ttu-id="4afd7-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4afd7-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4afd7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4afd7-113">HRESULT</span></span>|<span data-ttu-id="4afd7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4afd7-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4afd7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4afd7-115">S_OK</span></span>|<span data-ttu-id="4afd7-116">Es wurde versucht, alle Anforderungen zurückzusetzen. Das zurückgegebene Statusarray muss jedoch überprüft werden, um zu bestimmen, welche Funktionen erfolgreich zurücksetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="4afd7-116">An attempt was made to revert all requests; however, the returned status array must be checked to determine which functions were successfully reverted.</span></span>|  
|<span data-ttu-id="4afd7-117">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="4afd7-117">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="4afd7-118">Der Profiler muss die [ICorProfilerCallback4](icorprofilercallback4-interface.md) -Schnittstelle implementieren, damit dieser-Befehl unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4afd7-118">The profiler must implement the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="4afd7-119">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="4afd7-119">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="4afd7-120">Die JIT-Neukompilierung wurde nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4afd7-120">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="4afd7-121">Sie müssen die JIT-Neukompilierung während der Initialisierung aktivieren, indem Sie die [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) -Methode verwenden, um das `COR_PRF_ENABLE_REJIT`-Flag festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4afd7-121">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="4afd7-122">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4afd7-122">E_INVALIDARG</span></span>|<span data-ttu-id="4afd7-123">`cFunctions` ist 0, oder `moduleIds` oder `methodIds` ist `NULL`.</span><span class="sxs-lookup"><span data-stu-id="4afd7-123">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|<span data-ttu-id="4afd7-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4afd7-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4afd7-125">Die CLR konnte die Anforderung nicht abschließen, da nicht genügend Arbeitsspeicher vorhanden war.</span><span class="sxs-lookup"><span data-stu-id="4afd7-125">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="status-hresults"></a><span data-ttu-id="4afd7-126">Status HRESULTS</span><span class="sxs-lookup"><span data-stu-id="4afd7-126">Status HRESULTS</span></span>  
  
|<span data-ttu-id="4afd7-127">Statusarray HRESULT</span><span class="sxs-lookup"><span data-stu-id="4afd7-127">Status array HRESULT</span></span>|<span data-ttu-id="4afd7-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4afd7-128">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="4afd7-129">S_OK</span><span class="sxs-lookup"><span data-stu-id="4afd7-129">S_OK</span></span>|<span data-ttu-id="4afd7-130">Die entsprechende Funktion wurde erfolgreich zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4afd7-130">The corresponding function was successfully reverted.</span></span>|  
|<span data-ttu-id="4afd7-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4afd7-131">E_INVALIDARG</span></span>|<span data-ttu-id="4afd7-132">Der `moduleID`-Parameter oder der `methodDef`-Parameter ist `NULL`.</span><span class="sxs-lookup"><span data-stu-id="4afd7-132">The `moduleID` or `methodDef` parameter is `NULL`.</span></span>|  
|<span data-ttu-id="4afd7-133">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="4afd7-133">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="4afd7-134">Das Modul ist noch nicht vollständig geladen, oder es wird gerade entladen.</span><span class="sxs-lookup"><span data-stu-id="4afd7-134">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="4afd7-135">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="4afd7-135">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="4afd7-136">Das angegebene Modul wurde dynamisch generiert (z. B. durch `Reflection.Emit`).</span><span class="sxs-lookup"><span data-stu-id="4afd7-136">The specified module was dynamically generated (for example by `Reflection.Emit`).</span></span> <span data-ttu-id="4afd7-137">Daher wird es von dieser Methode nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4afd7-137">Therefore, it is not supported by this method.</span></span>|  
|<span data-ttu-id="4afd7-138">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="4afd7-138">CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND</span></span>|<span data-ttu-id="4afd7-139">Die angegebene Funktion konnte von der CLR nicht zurückgesetzt werden, da keine entsprechende aktive Neukompilierungsanforderung gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="4afd7-139">The CLR could not revert the specified function, because a corresponding active recompilation request was not found.</span></span> <span data-ttu-id="4afd7-140">Entweder wurde die Neukompilierung nie angefordert, oder die Funktion wurde bereits zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4afd7-140">Either the recompilation was never requested or the function was already reverted.</span></span>|  
|<span data-ttu-id="4afd7-141">Sonstige</span><span class="sxs-lookup"><span data-stu-id="4afd7-141">Other</span></span>|<span data-ttu-id="4afd7-142">Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4afd7-142">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="4afd7-143">Wenn beispielsweise ein Systemaufruf zum Ändern des Zugriffsschutz einer Speicherseite fehlschlägt, wird der Betriebssystemfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4afd7-143">For example, if a system call to change the access protection of a page of memory fails, the operating system error will be displayed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4afd7-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4afd7-144">Remarks</span></span>  
 <span data-ttu-id="4afd7-145">Beim nächsten Aufruf einer der zurückgesetzten Funktionsinstanzen werden die ursprünglichen Versionen der Funktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4afd7-145">The next time any of the revereted function instances are called, the original versions of the functions will be run.</span></span> <span data-ttu-id="4afd7-146">Wenn eine Funktion bereits ausgeführt wird, wird die Ausführung der aktiven Version abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4afd7-146">If a function is already running, it will finish executing the version that is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4afd7-147">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4afd7-147">Requirements</span></span>  
 <span data-ttu-id="4afd7-148">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4afd7-148">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4afd7-149">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4afd7-149">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4afd7-150">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4afd7-150">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4afd7-151">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4afd7-151">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4afd7-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4afd7-152">See also</span></span>

- [<span data-ttu-id="4afd7-153">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4afd7-153">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="4afd7-154">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4afd7-154">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4afd7-155">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="4afd7-155">Profiling</span></span>](index.md)
