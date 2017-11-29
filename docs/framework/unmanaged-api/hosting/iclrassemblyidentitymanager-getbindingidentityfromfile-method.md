---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 140240f5f108cdd26cd0e813d7fe47f102a3b941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="62930-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="62930-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="62930-103">Ruft die Identität der Assembly Binden von Daten für die Assembly im angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="62930-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62930-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62930-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62930-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62930-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="62930-106">[in] Der Pfad zu der Datei, die ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="62930-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="62930-107">[in] Der Wert der [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) Enumeration, der eine Assembly Identitätstyp angibt.</span><span class="sxs-lookup"><span data-stu-id="62930-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="62930-108">Für zukünftige Erweiterungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62930-108">Provided for future extensibility.</span></span> <span data-ttu-id="62930-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die common Language Runtime (CLR), Version 2.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="62930-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="62930-110">[out] Ein Puffer, der nicht transparenten Assembly Identitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="62930-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="62930-111">[in, out] Ein Zeiger auf die Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="62930-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62930-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62930-112">Return Value</span></span>  
  
|<span data-ttu-id="62930-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62930-113">HRESULT</span></span>|<span data-ttu-id="62930-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62930-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62930-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="62930-115">S_OK</span></span>|<span data-ttu-id="62930-116">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="62930-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="62930-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="62930-117">E_INVALIDARG</span></span>|<span data-ttu-id="62930-118">Die angegebene `pwzFilePath` ist null.</span><span class="sxs-lookup"><span data-stu-id="62930-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="62930-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="62930-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="62930-120">Die Größe des `pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="62930-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="62930-121">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="62930-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62930-122">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="62930-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62930-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62930-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62930-124">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="62930-124">The call timed out.</span></span>|  
|<span data-ttu-id="62930-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62930-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62930-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="62930-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62930-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62930-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62930-128">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="62930-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62930-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62930-129">E_FAIL</span></span>|<span data-ttu-id="62930-130">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="62930-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62930-131">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="62930-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62930-132">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="62930-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62930-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62930-133">Remarks</span></span>  
 <span data-ttu-id="62930-134">`GetBindingIdentityFromFile`wird in der Regel zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="62930-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="62930-135">Der erste Aufruf stellt einen null-Wert für `pwzBuffer`, und die Methode gibt die entsprechende Größe in `pcchBufferSize`.</span><span class="sxs-lookup"><span data-stu-id="62930-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="62930-136">Der beim zweiten Aufruf eines entsprechend reservierten Puffers und mit den Pufferdaten tatsächliche nach Abschluss gibt die Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="62930-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62930-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62930-137">Requirements</span></span>  
 <span data-ttu-id="62930-138">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62930-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62930-139">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62930-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62930-140">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="62930-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62930-141">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62930-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62930-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62930-142">See Also</span></span>  
 [<span data-ttu-id="62930-143">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62930-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="62930-144">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62930-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="62930-145">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62930-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
