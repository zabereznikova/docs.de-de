---
title: ICLRProfiling::AttachProfiler-Methode
ms.date: 03/30/2017
api_name:
- IClrProfiling.AttachProfiler Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- IClrProfiling::AttachProfiler
helpviewer_keywords:
- AttachProfiler method [.NET Framework profiling]
- IClrProfiling::AttachProfiler method [.NET Framework profiling]
ms.assetid: 535a6839-c443-405b-a6f4-e2af90725d5b
topic_type:
- apiref
ms.openlocfilehash: 48ac09e1862ae58e79707235e891f72920de1251
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500558"
---
# <a name="iclrprofilingattachprofiler-method"></a><span data-ttu-id="b58b1-102">ICLRProfiling::AttachProfiler-Methode</span><span class="sxs-lookup"><span data-stu-id="b58b1-102">ICLRProfiling::AttachProfiler Method</span></span>
<span data-ttu-id="b58b1-103">Fügt den angegebenen Profiler an den angegebenen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="b58b1-103">Attaches the specified profiler to the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b58b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b58b1-104">Syntax</span></span>  
  
```cpp  
HRESULT AttachProfiler(  
  [in] DWORD dwProfileeProcessID,  
  [in] DWORD dwMillisecondsMax,                     // optional  
  [in] const CLSID * pClsidProfiler,  
  [in] LPCWSTR wszProfilerPath,                     // optional  
  [in] size_is(cbClientData)] void * pvClientData,  // optional  
  [in] UINT cbClientData);                          // optional  
```  
  
## <a name="parameters"></a><span data-ttu-id="b58b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b58b1-105">Parameters</span></span>

- `dwProfileeProcessID`

  <span data-ttu-id="b58b1-106">\[in] die Prozess-ID des Prozesses, an den der Profiler angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58b1-106">\[in] The process ID of the process to which the profiler should be attached.</span></span> <span data-ttu-id="b58b1-107">Auf einem 64-Bit-Computer muss die Bitanzahl des profilierten Prozesses der Bitanzahl des Triggerprozesses entsprechen, von dem `AttachProfiler` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b58b1-107">On a 64-bit machine, the profiled process's bitness must match the bitness of the trigger process that is calling `AttachProfiler`.</span></span> <span data-ttu-id="b58b1-108">Wenn das Benutzerkonto, unter dem `AttachProfiler` aufgerufen wird, über Administratorrechte verfügt, kann der Zielprozess jeder Prozess im System sein.</span><span class="sxs-lookup"><span data-stu-id="b58b1-108">If the user account under which `AttachProfiler` is called has administrative privileges, the target process may be any process on the system.</span></span> <span data-ttu-id="b58b1-109">Andernfalls muss der Zielprozess im Besitz desselben Benutzerkontos sein.</span><span class="sxs-lookup"><span data-stu-id="b58b1-109">Otherwise, the target process must be owned by the same user account.</span></span>

- `dwMillisecondsMax`

  <span data-ttu-id="b58b1-110">\[in] die Zeitspanne (in Millisekunden) `AttachProfiler` bis zum Abschluss.</span><span class="sxs-lookup"><span data-stu-id="b58b1-110">\[in] The time duration, in milliseconds, for `AttachProfiler` to complete.</span></span> <span data-ttu-id="b58b1-111">Der Triggerprozess sollte ein Timeout übergeben, von dem bekannt ist, dass es für den Abschluss der Initialisierung des betreffenden Profilers ausreicht.</span><span class="sxs-lookup"><span data-stu-id="b58b1-111">The trigger process should pass a timeout that is known to be sufficient for the particular profiler to complete its initialization.</span></span>
  
- `pClsidProfiler`

  <span data-ttu-id="b58b1-112">\[in] ein Zeiger auf die CLSID des Profilers, der geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58b1-112">\[in] A pointer to the CLSID of the profiler to be loaded.</span></span> <span data-ttu-id="b58b1-113">Der Triggerprozess kann diesen Arbeitsspeicher wiederverwenden, nachdem `AttachProfiler` beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b58b1-113">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span>

- `wszProfilerPath`

  <span data-ttu-id="b58b1-114">\[in] der vollständige Pfad zur DLL-Datei des Profilers, die geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b58b1-114">\[in] The full path to the profiler’s DLL file to be loaded.</span></span> <span data-ttu-id="b58b1-115">Diese Zeichenfolge darf, einschließlich des NULL-Abschlusszeichens, nicht mehr als 260 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b58b1-115">This string should contain no more than 260 characters, including the null terminator.</span></span> <span data-ttu-id="b58b1-116">Wenn `wszProfilerPath` gleich NULL oder eine leere Zeichenfolge ist, versucht die Common Language Runtime (CLR), den Speicherort der DLL-Datei des Profilers zu ermitteln, indem sie in der Registrierung nach der CLSID von diesem `pClsidProfiler` sucht.</span><span class="sxs-lookup"><span data-stu-id="b58b1-116">If `wszProfilerPath` is null or an empty string, the common language runtime (CLR) will try to find the location of the profiler’s DLL file by looking in the registry for the CLSID that `pClsidProfiler` points to.</span></span>

- `pvClientData`

  <span data-ttu-id="b58b1-117">\[in] ein Zeiger auf Daten, die von der [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) -Methode an den Profiler übermittelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b58b1-117">\[in] A pointer to data to be passed to the profiler by the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method.</span></span> <span data-ttu-id="b58b1-118">Der Triggerprozess kann diesen Arbeitsspeicher wiederverwenden, nachdem `AttachProfiler` beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b58b1-118">The trigger process can reuse this memory after `AttachProfiler` returns.</span></span> <span data-ttu-id="b58b1-119">Wenn `pvClientData` gleich NULL ist, muss `cbClientData` gleich 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="b58b1-119">If `pvClientData` is null, `cbClientData` must be 0 (zero).</span></span>

- `cbClientData`

  <span data-ttu-id="b58b1-120">\[in] die Größe der Daten in Bytes, `pvClientData` auf die verweist.</span><span class="sxs-lookup"><span data-stu-id="b58b1-120">\[in] The size, in bytes, of the data that `pvClientData` points to.</span></span>

## <a name="return-value"></a><span data-ttu-id="b58b1-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b58b1-121">Return Value</span></span>  
 <span data-ttu-id="b58b1-122">Diese Methode gibt die folgenden HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="b58b1-122">This method returns the following HRESULTs.</span></span>  
  
|<span data-ttu-id="b58b1-123">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b58b1-123">HRESULT</span></span>|<span data-ttu-id="b58b1-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b58b1-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b58b1-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="b58b1-125">S_OK</span></span>|<span data-ttu-id="b58b1-126">Der angegebene Profiler wurde erfolgreich an den Zielprozess angefügt.</span><span class="sxs-lookup"><span data-stu-id="b58b1-126">The specified profiler has successfully attached to the target process.</span></span>|  
|<span data-ttu-id="b58b1-127">CORPROF_E_PROFILER_ALREADY_ACTIVE</span><span class="sxs-lookup"><span data-stu-id="b58b1-127">CORPROF_E_PROFILER_ALREADY_ACTIVE</span></span>|<span data-ttu-id="b58b1-128">Es ist bereits ein Profiler aktiv, oder es wird bereits ein Profiler an den Zielprozess angefügt.</span><span class="sxs-lookup"><span data-stu-id="b58b1-128">There is already a profiler active or attaching to the target process.</span></span>|  
|<span data-ttu-id="b58b1-129">CORPROF_E_PROFILER_NOT_ATTACHABLE</span><span class="sxs-lookup"><span data-stu-id="b58b1-129">CORPROF_E_PROFILER_NOT_ATTACHABLE</span></span>|<span data-ttu-id="b58b1-130">Anfügen wird vom angegebenen Profiler nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b58b1-130">The specified profiler does not support attachment.</span></span> <span data-ttu-id="b58b1-131">Der Triggerprozess versucht möglicherweise, einen anderen Profiler anzufügen.</span><span class="sxs-lookup"><span data-stu-id="b58b1-131">The trigger process may attempt to attach a different profiler.</span></span>|  
|<span data-ttu-id="b58b1-132">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span><span class="sxs-lookup"><span data-stu-id="b58b1-132">CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER</span></span>|<span data-ttu-id="b58b1-133">Das Anfügen eines Profilers kann nicht angefordert werden, da die Version des Zielprozesses nicht mit dem aktuellen Prozess kompatibel ist, von dem `AttachProfiler` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b58b1-133">Unable to request a profiler attachment, because the version of the target process is incompatible with the current process that is calling `AttachProfiler`.</span></span>|  
|<span data-ttu-id="b58b1-134">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span><span class="sxs-lookup"><span data-stu-id="b58b1-134">HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)</span></span>|<span data-ttu-id="b58b1-135">Der Benutzer des Triggerprozesses hat keinen Zugriff auf den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="b58b1-135">The user of the trigger process does not have access to the target process.</span></span>|  
|<span data-ttu-id="b58b1-136">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span><span class="sxs-lookup"><span data-stu-id="b58b1-136">HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)</span></span>|<span data-ttu-id="b58b1-137">Der Benutzer des Triggerprozesses hat nicht die erforderlichen Rechte, um einen Profiler an den angegebenen Zielprozess anzufügen.</span><span class="sxs-lookup"><span data-stu-id="b58b1-137">The user of the trigger process does not have the privileges necessary to attach a profiler to the given target process.</span></span> <span data-ttu-id="b58b1-138">Das Anwendungsereignisprotokoll enthält möglicherweise weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="b58b1-138">The application event log may contain more information.</span></span>|  
|<span data-ttu-id="b58b1-139">CORPROF_E_IPC_FAILED</span><span class="sxs-lookup"><span data-stu-id="b58b1-139">CORPROF_E_IPC_FAILED</span></span>|<span data-ttu-id="b58b1-140">Fehler bei der Kommunikation mit dem Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="b58b1-140">A failure occurred when communicating with the target process.</span></span> <span data-ttu-id="b58b1-141">Dies geschieht häufig, wenn der Zielprozess heruntergefahren wurde.</span><span class="sxs-lookup"><span data-stu-id="b58b1-141">This commonly happens if the target process was shutting down.</span></span>|  
|<span data-ttu-id="b58b1-142">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="b58b1-142">HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)</span></span>|<span data-ttu-id="b58b1-143">Der Zielprozess ist nicht vorhanden oder führt keine CLR aus, die Anfügen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b58b1-143">The target process does not exist or is not running a CLR that supports attachment.</span></span> <span data-ttu-id="b58b1-144">Dies kann darauf hinweisen, dass die CLR seit dem Aufruf von der Runtime-Enumerationsmethode entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b58b1-144">This may indicate that the CLR was unloaded since the call to the runtime enumeration method.</span></span>|  
|<span data-ttu-id="b58b1-145">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span><span class="sxs-lookup"><span data-stu-id="b58b1-145">HRESULT_FROM_WIN32(ERROR_TIMEOUT)</span></span>|<span data-ttu-id="b58b1-146">Das Timeout ist abgelaufen, ohne dass mit dem Laden des Profilers begonnen wurde.</span><span class="sxs-lookup"><span data-stu-id="b58b1-146">The timeout expired without beginning to load the profiler.</span></span> <span data-ttu-id="b58b1-147">Sie können den Anfügevorgang wiederholen.</span><span class="sxs-lookup"><span data-stu-id="b58b1-147">You can retry the attach operation.</span></span> <span data-ttu-id="b58b1-148">Timeouts treten auf, wenn ein Finalizer im Zielprozess für einen längeren Zeitraum als durch den Timeoutwert angegeben ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b58b1-148">Timeouts occur when a finalizer in the target process runs for a longer time than the timeout value.</span></span>|  
|<span data-ttu-id="b58b1-149">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b58b1-149">E_INVALIDARG</span></span>|<span data-ttu-id="b58b1-150">Mindestens ein Parameter hat ungültige Werte.</span><span class="sxs-lookup"><span data-stu-id="b58b1-150">One or more parameters have invalid values.</span></span>|  
|<span data-ttu-id="b58b1-151">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b58b1-151">E_FAIL</span></span>|<span data-ttu-id="b58b1-152">Ein anderer, nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b58b1-152">Some other, unspecified failure occurred.</span></span>|  
|<span data-ttu-id="b58b1-153">Sonstige Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="b58b1-153">Other error codes</span></span>|<span data-ttu-id="b58b1-154">Wenn die [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) -Methode des Profilers ein HRESULT zurückgibt, das einen Fehler angibt, wird `AttachProfiler` dieses HRESULT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b58b1-154">If the profiler’s [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method returns an HRESULT that indicates failure, `AttachProfiler` returns that same HRESULT.</span></span> <span data-ttu-id="b58b1-155">In diesem Fall wird E_NOTIMPL in CORPROF_E_PROFILER_NOT_ATTACHABLE konvertiert.</span><span class="sxs-lookup"><span data-stu-id="b58b1-155">In this case, E_NOTIMPL is converted to CORPROF_E_PROFILER_NOT_ATTACHABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b58b1-156">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b58b1-156">Remarks</span></span>  
  
## <a name="memory-management"></a><span data-ttu-id="b58b1-157">Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="b58b1-157">Memory Management</span></span>  
 <span data-ttu-id="b58b1-158">Entsprechend den COM-Konventionen ist der Aufrufer von `AttachProfiler` (z. B. der vom Profilerentwickler erstellte Triggercode) für das Zuordnen und Freigeben des Arbeitsspeichers für die Daten zuständig, auf die der `pvClientData`-Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="b58b1-158">In keeping with COM conventions, the caller of `AttachProfiler` (for example, the trigger code authored by the profiler developer) is responsible for allocating and de-allocating the memory for the data that the `pvClientData` parameter points to.</span></span> <span data-ttu-id="b58b1-159">Wenn die CLR den `AttachProfiler`-Aufruf ausführt, erstellt sie eine Kopie des Arbeitsspeichers, auf den `pvClientData` verweist, und sie überträgt die Kopie an den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="b58b1-159">When the CLR executes the `AttachProfiler` call, it makes a copy of the memory that `pvClientData` points to and transmits it to the target process.</span></span> <span data-ttu-id="b58b1-160">Wenn die CLR im Zielprozess ihre eigene Kopie des `pvClientData`-Blocks empfängt, übergibt sie den Block über die `InitializeForAttach`-Methode an den Profiler, und dann gibt sie ihre Kopie der `pvClientData`-Blocks aus dem Zielprozess frei.</span><span class="sxs-lookup"><span data-stu-id="b58b1-160">When the CLR inside the target process receives its own copy of the `pvClientData` block, it passes the block to the profiler through the `InitializeForAttach` method, and then deallocates its copy of the `pvClientData` block from the target process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b58b1-161">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b58b1-161">Requirements</span></span>  
 <span data-ttu-id="b58b1-162">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b58b1-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b58b1-163">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b58b1-163">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b58b1-164">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b58b1-164">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b58b1-165">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b58b1-165">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58b1-166">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b58b1-166">See also</span></span>

- [<span data-ttu-id="b58b1-167">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b58b1-167">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b58b1-168">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b58b1-168">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b58b1-169">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b58b1-169">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b58b1-170">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="b58b1-170">Profiling</span></span>](index.md)
