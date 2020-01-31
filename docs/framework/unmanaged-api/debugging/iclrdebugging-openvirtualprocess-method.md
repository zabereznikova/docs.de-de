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
ms.openlocfilehash: 585b3d605d0df9169c12ca10198846ec0a7fe6d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793611"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="31f07-102">ICLRDebugging::OpenVirtualProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="31f07-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="31f07-103">Ruft die ICorDebugProcess-Schnittstelle ab, die einem Common Language Runtime (CLR)-Modul entspricht, das in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="31f07-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31f07-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="31f07-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="31f07-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="31f07-106">in Die Basisadresse eines Moduls im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="31f07-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="31f07-107">COR_E_NOT_CLR wird zurückgegeben, wenn das angegebene Modul kein CLR-Modul ist.</span><span class="sxs-lookup"><span data-stu-id="31f07-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="31f07-108">in Eine Daten Ziel Abstraktion, die es dem verwalteten Debugger ermöglicht, den Prozessstatus zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="31f07-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="31f07-109">Der Debugger muss die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="31f07-109">The debugger must implement the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="31f07-110">Sie sollten die [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle implementieren, um Szenarios zu unterstützen, in denen die CLR, die gedebuggt wird, nicht lokal auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="31f07-110">You should implement the [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="31f07-111">in Eine Bibliotheks Anbieter-Rückruf Schnittstelle, die es ermöglicht, versionsspezifische Debugbibliotheken nach Bedarf zu finden und zu laden.</span><span class="sxs-lookup"><span data-stu-id="31f07-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="31f07-112">Dieser Parameter ist nur erforderlich, wenn `ppProcess` oder `pFlags` nicht `null`ist.</span><span class="sxs-lookup"><span data-stu-id="31f07-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="31f07-113">in Die höchste Version der CLR, die von diesem Debugger debuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="31f07-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="31f07-114">Geben Sie die Haupt-, neben-und Buildversionen aus der aktuellen CLR-Version an, die dieser Debugger unterstützt, und legen Sie die Revisionsnummer auf 65535 fest, um zukünftige direkte CLR-Wartungs Releases zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="31f07-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="31f07-115">in Die ID der abzurufenden ICorDebugProcess-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="31f07-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="31f07-116">Zurzeit sind die einzigen akzeptierten Werte IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 und IID_CORDEBUGPROCESS.</span><span class="sxs-lookup"><span data-stu-id="31f07-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="31f07-117">vorgenommen Ein Zeiger auf die COM-Schnittstelle, die durch `riidProcess`identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="31f07-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="31f07-118">[in, out] Die Version der CLR.</span><span class="sxs-lookup"><span data-stu-id="31f07-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="31f07-119">Bei der Eingabe kann dieser Wert `null`werden.</span><span class="sxs-lookup"><span data-stu-id="31f07-119">On input, this value can be `null`.</span></span> <span data-ttu-id="31f07-120">Sie kann auch auf eine [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) Struktur verweisen. in diesem Fall muss das `wStructVersion` Feld der Struktur mit 0 (null) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="31f07-120">It can also point to a [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="31f07-121">Bei der Ausgabe wird die zurückgegebene `CLR_DEBUGGING_VERSION` Struktur mit den Versionsinformationen für die CLR ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="31f07-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="31f07-122">vorgenommen Informationsflags für die angegebene Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="31f07-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="31f07-123">Eine Beschreibung der Flags finden Sie im [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="31f07-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31f07-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31f07-124">Return Value</span></span>  
 <span data-ttu-id="31f07-125">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="31f07-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="31f07-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31f07-126">HRESULT</span></span>|<span data-ttu-id="31f07-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31f07-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31f07-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="31f07-128">S_OK</span></span>|<span data-ttu-id="31f07-129">Die Methode wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="31f07-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="31f07-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="31f07-130">E_POINTER</span></span>|<span data-ttu-id="31f07-131">`pDataTarget` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="31f07-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="31f07-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="31f07-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="31f07-133">Der [iclrbinbugginglibraryprovider](iclrdebugginglibraryprovider-interface.md) -Rückruf gibt einen Fehler zurück oder stellt kein gültiges Handle bereit.</span><span class="sxs-lookup"><span data-stu-id="31f07-133">The [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="31f07-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="31f07-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="31f07-135">`pDataTarget` implementiert die erforderlichen Daten Ziel Schnittstellen für diese Version der Laufzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="31f07-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="31f07-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="31f07-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="31f07-137">Das gekennzeichnete Modul ist kein CLR-Modul.</span><span class="sxs-lookup"><span data-stu-id="31f07-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="31f07-138">Dieses HRESULT wird auch zurückgegeben, wenn ein CLR-Modul nicht erkannt werden kann, weil der Arbeitsspeicher beschädigt ist, das Modul nicht verfügbar ist oder die CLR-Version höher als die Shim-Version ist.</span><span class="sxs-lookup"><span data-stu-id="31f07-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="31f07-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="31f07-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="31f07-140">Dieses debugingmodell wird von dieser Laufzeitversion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31f07-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="31f07-141">Derzeit wird das debugingmodell von CLR-Versionen vor dem .NET Framework 4 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31f07-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="31f07-142">Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31f07-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="31f07-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="31f07-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="31f07-144">Die CLR-Version ist größer als die Version, die dieser Debugger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31f07-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="31f07-145">Der `pwszVersion` Output-Parameter ist nach diesem Fehler weiterhin auf den korrekten Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31f07-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="31f07-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="31f07-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="31f07-147">Die `riidProcess`-Schnittstelle ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="31f07-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="31f07-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="31f07-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="31f07-149">Die `CLR_DEBUGGING_VERSION` Struktur hat keinen erkannten Wert für `wStructVersion`.</span><span class="sxs-lookup"><span data-stu-id="31f07-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="31f07-150">Der einzige akzeptierte Wert ist zu diesem Zeitpunkt 0.</span><span class="sxs-lookup"><span data-stu-id="31f07-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="31f07-151">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="31f07-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31f07-152">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31f07-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f07-153">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31f07-153">Requirements</span></span>  
 <span data-ttu-id="31f07-154">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31f07-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f07-155">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31f07-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31f07-156">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31f07-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31f07-157">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f07-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f07-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31f07-158">See also</span></span>

- [<span data-ttu-id="31f07-159">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="31f07-159">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="31f07-160">Debuggen</span><span class="sxs-lookup"><span data-stu-id="31f07-160">Debugging</span></span>](index.md)
