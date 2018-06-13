---
title: ICLRDebugging::OpenVirtualProcess-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51b5a9ecd85f0d40ac2fe2826cbbe7a56a6228d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408251"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="15f59-102">ICLRDebugging::OpenVirtualProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="15f59-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="15f59-103">Ruft die ICorDebugProcess-Schnittstelle, die eine common Language Runtime (CLR)-Modul im Prozess geladenen entspricht.</span><span class="sxs-lookup"><span data-stu-id="15f59-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15f59-104">Syntax</span></span>  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15f59-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15f59-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="15f59-106">[in] Die Basisadresse eines Moduls im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="15f59-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="15f59-107">COR_E_NOT_CLR wird zurückgegeben, wenn das angegebene Modul kein CLR-Modul ist.</span><span class="sxs-lookup"><span data-stu-id="15f59-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="15f59-108">[in] Der Abstraktion eines Daten-Ziel, das den verwalteten Debugger Prozessstatus überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="15f59-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="15f59-109">Der Debugger muss implementieren die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="15f59-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="15f59-110">Implementieren Sie die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) -Schnittstelle zur Unterstützung von Szenarien, in denen die CLR, die gedebuggt wird ist nicht lokal auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="15f59-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="15f59-111">[in] Eine Bibliothek Rückrufschnittstelle, die es ermöglicht, versionsspezifische-Debugbibliotheken Nachfrage gefunden und geladen werden.</span><span class="sxs-lookup"><span data-stu-id="15f59-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="15f59-112">Dieser Parameter ist erforderlich, wenn nur `ppProcess` oder `pFlags` nicht `null`.</span><span class="sxs-lookup"><span data-stu-id="15f59-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="15f59-113">[in] Die höchste Version der CLR, die diesen Debugger Debuggen kann.</span><span class="sxs-lookup"><span data-stu-id="15f59-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="15f59-114">Sie sollten geben Haupt-oder Nebenversion, und Buildversionen aus der aktuellen CLR-Version, die dieser Debugger unterstützt, und legen die Revisionsnummer auf 65.535 ein, um zukünftige direktes CLR Wartung Versionen aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="15f59-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="15f59-115">[in] Die ID der ICorDebugProcess-Schnittstelle zum Abrufen.</span><span class="sxs-lookup"><span data-stu-id="15f59-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="15f59-116">Aktuell sind die einzigen zulässigen Werte IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="15f59-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="15f59-117">[out] Ein Zeiger auf die COM-Schnittstelle, die identifizierte `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="15f59-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="15f59-118">[in, out] Die Version der CLR.</span><span class="sxs-lookup"><span data-stu-id="15f59-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="15f59-119">Dieser Wert kann bei der Eingabe, sein `null`.</span><span class="sxs-lookup"><span data-stu-id="15f59-119">On input, this value can be `null`.</span></span> <span data-ttu-id="15f59-120">Es kann auch zeigen Sie auf eine [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Struktur, in diesem Fall der Struktur `wStructVersion` -Feld auf 0 (null) initialisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="15f59-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="15f59-121">Bei der Ausgabe der zurückgegebenen `CLR_DEBUGGING_VERSION` Struktur wird mit der die Versionsinformationen für die CLR gefüllt.</span><span class="sxs-lookup"><span data-stu-id="15f59-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="15f59-122">[out] Nur zu Informationszwecken Flags zu dem angegebenen Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="15f59-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="15f59-123">Finden Sie unter der [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) Thema eine Beschreibung der Flags.</span><span class="sxs-lookup"><span data-stu-id="15f59-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15f59-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15f59-124">Return Value</span></span>  
 <span data-ttu-id="15f59-125">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="15f59-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="15f59-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15f59-126">HRESULT</span></span>|<span data-ttu-id="15f59-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15f59-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15f59-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="15f59-128">S_OK</span></span>|<span data-ttu-id="15f59-129">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="15f59-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="15f59-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="15f59-130">E_POINTER</span></span>|<span data-ttu-id="15f59-131">`pDataTarget` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="15f59-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="15f59-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="15f59-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="15f59-133">Die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Rückruf einen Fehler zurück, oder ein gültiges Handle werden nicht bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="15f59-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="15f59-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="15f59-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="15f59-135">`pDataTarget` implementiert nicht die erforderlichen Daten Ziel-Schnittstellen für diese Version der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="15f59-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="15f59-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="15f59-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="15f59-137">Das angegebene Modul ist kein CLR-Modul.</span><span class="sxs-lookup"><span data-stu-id="15f59-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="15f59-138">Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht ermittelt werden kann, da der Arbeitsspeicher ist beschädigt, das Modul ist nicht verfügbar oder die CLR-Version ist neuer als die Shimversion.</span><span class="sxs-lookup"><span data-stu-id="15f59-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="15f59-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="15f59-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="15f59-140">Diese Version der Common Language Runtime unterstützt diese debuggingmodell nicht.</span><span class="sxs-lookup"><span data-stu-id="15f59-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="15f59-141">Die debuggingmodell wird derzeit nicht unterstützt, von CLR-Versionen vor der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15f59-141">Currently, the debugging model is not supported by CLR versions before the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="15f59-142">Die `pwszVersion` Output-Parameter nach diesem Fehler noch auf den richtigen Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="15f59-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="15f59-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="15f59-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="15f59-144">Die Version der CLR ist größer als die Version, die dieser Debugger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15f59-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="15f59-145">Die `pwszVersion` Output-Parameter nach diesem Fehler noch auf den richtigen Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="15f59-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="15f59-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="15f59-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="15f59-147">Die `riidProcess` Schnittstelle ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="15f59-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="15f59-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="15f59-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="15f59-149">Die `CLR_DEBUGGING_VERSION` Struktur verfügt nicht über einen gültigen Wert für `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="15f59-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="15f59-150">Der einzige akzeptierte Wert zu diesem Zeitpunkt ist 0.</span><span class="sxs-lookup"><span data-stu-id="15f59-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="15f59-151">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="15f59-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15f59-152">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15f59-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f59-153">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15f59-153">Requirements</span></span>  
 <span data-ttu-id="15f59-154">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f59-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f59-155">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15f59-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15f59-156">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15f59-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15f59-157">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f59-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f59-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15f59-158">See Also</span></span>  
 [<span data-ttu-id="15f59-159">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="15f59-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="15f59-160">Debuggen</span><span class="sxs-lookup"><span data-stu-id="15f59-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
