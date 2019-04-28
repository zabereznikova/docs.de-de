---
title: ICLRDebuggingLibraryProvider::ProvideLibrary-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f5d44b6497e971e6d1ed030c043b91b88c070b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697806"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="d7e26-102">ICLRDebuggingLibraryProvider::ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="d7e26-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="d7e26-103">Ruft eine Bibliotheksanbieter-Rückrufschnittstelle, die es common Language Runtime (CLR) hängt von der Version Debugbibliotheken ermöglicht zu suchen und zu laden, auf Anforderung ab.</span><span class="sxs-lookup"><span data-stu-id="d7e26-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7e26-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7e26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7e26-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="d7e26-106">[in] Der Name des Moduls, das angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="d7e26-106">[in] The name of the module being requested.</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="d7e26-107">[in] Die Datums-/ Zeitstempel im COFF-Dateiheader der PE-Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d7e26-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="d7e26-108">[in] Die `SizeOfImage` Feld in der optionalen COFF-Dateiheader der PE-Dateien gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d7e26-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="d7e26-109">[out] Das Handle für das angeforderte Modul.</span><span class="sxs-lookup"><span data-stu-id="d7e26-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7e26-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7e26-110">Return Value</span></span>  
 <span data-ttu-id="d7e26-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7e26-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d7e26-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7e26-112">HRESULT</span></span>|<span data-ttu-id="d7e26-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7e26-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7e26-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7e26-114">S_OK</span></span>|<span data-ttu-id="d7e26-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d7e26-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d7e26-116">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="d7e26-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7e26-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7e26-117">Remarks</span></span>  
 <span data-ttu-id="d7e26-118">`ProvideLibrary` ermöglicht dem Debugger, Module bereitzustellen, die für das Debuggen von bestimmten CLR-Dateien wie z. B. "mscordbi.dll" und mscordacwks.dll erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d7e26-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="d7e26-119">Die Modul-Handles zu haben, gültig bleiben, bis ein Aufruf der [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) -Methode gibt an, dass sie freigegeben werden können, die an diesem Punkt wird es der Verantwortung des Aufrufers, die Handles freizugeben.</span><span class="sxs-lookup"><span data-stu-id="d7e26-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="d7e26-120">Der Debugger können Sie alle verfügbaren Verfahren suchen oder die debugging-Modul bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="d7e26-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7e26-121">Dieses Feature ermöglicht den API-Aufrufer, Module bereitzustellen, die ausführbare Datei, und möglicherweise böswilligen Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7e26-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="d7e26-122">Als Sicherheitsmaßnahme, der Aufrufer nicht verwenden sollten `ProvideLibrary` keinen Code zu verteilen, dass es nicht selbst ausführen.</span><span class="sxs-lookup"><span data-stu-id="d7e26-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="d7e26-123">Wenn ein ernsthaftes Sicherheitsproblem an einem bereits freigegebenen Bibliothek, z. B. mscordbi.dll oder mscordacwks.dll, erkannt wird, kann das Shim gepatcht werden, so, dass um die fehlerhaften Versionen der Dateien zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="d7e26-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="d7e26-124">Das Shim kann Anforderungen für die gepatchten Versionen der Dateien ausgegeben und die ungültigen Versionen ablehnen, wenn sie als Antwort auf jede Anforderung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d7e26-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="d7e26-125">Dies kann auftreten, nur dann, wenn der Benutzer auf eine neue Version des Shims gepatcht wurde.</span><span class="sxs-lookup"><span data-stu-id="d7e26-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="d7e26-126">Nicht gepatchte Versionen bleiben ein Sicherheitsrisiko.</span><span class="sxs-lookup"><span data-stu-id="d7e26-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7e26-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7e26-127">Requirements</span></span>  
 <span data-ttu-id="d7e26-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7e26-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7e26-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7e26-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7e26-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7e26-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7e26-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7e26-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e26-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7e26-132">See also</span></span>

- [<span data-ttu-id="d7e26-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d7e26-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d7e26-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d7e26-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
