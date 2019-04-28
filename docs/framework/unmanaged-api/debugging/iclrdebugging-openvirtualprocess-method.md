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
ms.openlocfilehash: a313ea62455067fb36b94d942b0ce21589677e3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698160"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="f45ad-102">ICLRDebugging::OpenVirtualProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="f45ad-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="f45ad-103">Ruft ab, der ICorDebugProcess-Schnittstelle, die eine common Language Runtime (CLR)-Modul in den Prozess geladenen entspricht.</span><span class="sxs-lookup"><span data-stu-id="f45ad-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f45ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f45ad-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f45ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f45ad-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="f45ad-106">[in] Die Basisadresse eines Moduls in den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="f45ad-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="f45ad-107">COR_E_NOT_CLR wird zurückgegeben, wenn das angegebene Modul kein CLR-Modul ist.</span><span class="sxs-lookup"><span data-stu-id="f45ad-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="f45ad-108">[in] Eine Abstraktion der Daten-Ziel, die mit dem verwalteten Debugger Prozessstatus überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="f45ad-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="f45ad-109">Der Debugger muss implementieren die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f45ad-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="f45ad-110">Implementieren Sie die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Schnittstelle zur Unterstützung von Szenarien, in denen die CLR, die gedebuggt wird nicht lokal auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f45ad-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="f45ad-111">[in] Eine Bibliothek Rückrufschnittstelle, die es, versionsspezifische-Debugbibliotheken ermöglicht auf Nachfrage gefunden und geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f45ad-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="f45ad-112">Dieser Parameter ist erforderlich, wenn `ppProcess` oder `pFlags` nicht `null`.</span><span class="sxs-lookup"><span data-stu-id="f45ad-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="f45ad-113">[in] Die höchste Version der CLR, die von diesem Debugger Debuggen kann.</span><span class="sxs-lookup"><span data-stu-id="f45ad-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="f45ad-114">Sie sollten Geben Sie die Hauptversion, Nebenversion, build-Versionen aus der aktuellen CLR-Version, die dieser Debugger unterstützt und legen Sie die Revisionsnummer und 65535 liegen, um zukünftige direktes CLR Wartungsversionen zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f45ad-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="f45ad-115">[in] Die ID der ICorDebugProcess-Schnittstelle, abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f45ad-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="f45ad-116">Derzeit werden nur die Werte, IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="f45ad-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="f45ad-117">[out] Ein Zeiger auf die COM-Schnittstelle, die identifizierte `riidProcess`.</span><span class="sxs-lookup"><span data-stu-id="f45ad-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f45ad-118">[in, out] Die Version der CLR.</span><span class="sxs-lookup"><span data-stu-id="f45ad-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="f45ad-119">Dieser Wert kann bei der Eingabe, sein `null`.</span><span class="sxs-lookup"><span data-stu-id="f45ad-119">On input, this value can be `null`.</span></span> <span data-ttu-id="f45ad-120">Sie können auch zeigen Sie auf eine [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Struktur, in diesem Fall der Struktur `wStructVersion` Feld muss mit 0 (null) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f45ad-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="f45ad-121">Bei Ausgabe ist das zurückgegebene `CLR_DEBUGGING_VERSION` Struktur wird mit der die Versionsinformationen für die CLR gefüllt.</span><span class="sxs-lookup"><span data-stu-id="f45ad-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="f45ad-122">[out] Nur zu Informationszwecken Flags über die angegebene Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="f45ad-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="f45ad-123">Finden Sie unter den [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) Thema eine Beschreibung der Flags.</span><span class="sxs-lookup"><span data-stu-id="f45ad-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f45ad-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f45ad-124">Return Value</span></span>  
 <span data-ttu-id="f45ad-125">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f45ad-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f45ad-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f45ad-126">HRESULT</span></span>|<span data-ttu-id="f45ad-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f45ad-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f45ad-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="f45ad-128">S_OK</span></span>|<span data-ttu-id="f45ad-129">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f45ad-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="f45ad-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f45ad-130">E_POINTER</span></span>|<span data-ttu-id="f45ad-131">`pDataTarget` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="f45ad-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="f45ad-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="f45ad-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="f45ad-133">Die [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Rückruf einen Fehler zurück oder stellt kein gültiges Handle.</span><span class="sxs-lookup"><span data-stu-id="f45ad-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="f45ad-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="f45ad-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="f45ad-135">`pDataTarget` implementiert die Schnittstellen für erforderliche Ziel für diese Version der Laufzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="f45ad-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="f45ad-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="f45ad-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="f45ad-137">Das angegebene Modul ist es sich nicht um ein CLR-Modul.</span><span class="sxs-lookup"><span data-stu-id="f45ad-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="f45ad-138">Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht ermittelt werden kann, da der Arbeitsspeicher ist beschädigt, das Modul ist nicht verfügbar oder die CLR-Version ist neuer als die Shimversion.</span><span class="sxs-lookup"><span data-stu-id="f45ad-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="f45ad-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="f45ad-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="f45ad-140">Diese Runtime-Version wird dieses Modell Debuggen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f45ad-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="f45ad-141">Das Debuggen Modell ist derzeit nicht unterstützt, von der CLR-Versionen vor der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f45ad-141">Currently, the debugging model is not supported by CLR versions before the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="f45ad-142">Die `pwszVersion` Output-Parameter wird nach dem dieser Fehler weiterhin auf den richtigen Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f45ad-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="f45ad-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="f45ad-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="f45ad-144">Die Version der CLR ist größer als die Version, die dieser Debugger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f45ad-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="f45ad-145">Die `pwszVersion` Output-Parameter wird nach dem dieser Fehler weiterhin auf den richtigen Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f45ad-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="f45ad-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="f45ad-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="f45ad-147">Die `riidProcess` Schnittstelle ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f45ad-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="f45ad-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="f45ad-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="f45ad-149">Die `CLR_DEBUGGING_VERSION` Struktur verfügt nicht über keinen gültigen Wert für `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="f45ad-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="f45ad-150">Der einzige akzeptierte Wert zu diesem Zeitpunkt ist 0.</span><span class="sxs-lookup"><span data-stu-id="f45ad-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f45ad-151">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="f45ad-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f45ad-152">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f45ad-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f45ad-153">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f45ad-153">Requirements</span></span>  
 <span data-ttu-id="f45ad-154">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f45ad-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f45ad-155">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f45ad-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f45ad-156">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f45ad-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f45ad-157">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f45ad-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f45ad-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f45ad-158">See also</span></span>

- [<span data-ttu-id="f45ad-159">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f45ad-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f45ad-160">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f45ad-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
