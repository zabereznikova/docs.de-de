---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3d5e53dd0845fbd01dbd9d20ce8feef12748c04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213922"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="b3a73-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="b3a73-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="b3a73-103">Ruft die Identität der Assembly Binden von Daten für die Assembly im angegebenen Dateipfad ab.</span><span class="sxs-lookup"><span data-stu-id="b3a73-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3a73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3a73-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3a73-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3a73-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="b3a73-106">[in] Der Pfad zur Datei, die ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="b3a73-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b3a73-107">[in] Der Wert der [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) Enumeration, der Typ der Identität einer Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="b3a73-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="b3a73-108">Für eine zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b3a73-108">Provided for future extensibility.</span></span> <span data-ttu-id="b3a73-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die common Language Runtime (CLR) Version 2.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b3a73-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="b3a73-110">[out] Ein Puffer mit nicht transparenten Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="b3a73-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="b3a73-111">[in, out] Ein Zeiger auf die Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="b3a73-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3a73-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b3a73-112">Return Value</span></span>  
  
|<span data-ttu-id="b3a73-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3a73-113">HRESULT</span></span>|<span data-ttu-id="b3a73-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3a73-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3a73-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3a73-115">S_OK</span></span>|<span data-ttu-id="b3a73-116">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b3a73-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="b3a73-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b3a73-117">E_INVALIDARG</span></span>|<span data-ttu-id="b3a73-118">Die angegebene `pwzFilePath` ist null.</span><span class="sxs-lookup"><span data-stu-id="b3a73-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="b3a73-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b3a73-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b3a73-120">Die Größe des `pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="b3a73-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="b3a73-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3a73-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3a73-122">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b3a73-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3a73-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3a73-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3a73-124">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b3a73-124">The call timed out.</span></span>|  
|<span data-ttu-id="b3a73-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3a73-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3a73-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b3a73-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3a73-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3a73-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3a73-128">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="b3a73-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3a73-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3a73-129">E_FAIL</span></span>|<span data-ttu-id="b3a73-130">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b3a73-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3a73-131">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3a73-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3a73-132">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b3a73-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3a73-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3a73-133">Remarks</span></span>  
 <span data-ttu-id="b3a73-134">`GetBindingIdentityFromFile` wird in der Regel zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b3a73-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="b3a73-135">Der erste Aufruf stellt einen null-Wert für `pwzBuffer`, und die Methode gibt die richtige Größe in `pcchBufferSize`.</span><span class="sxs-lookup"><span data-stu-id="b3a73-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="b3a73-136">Beim zweiten Aufruf wird einen ordnungsgemäß zugewiesenen Puffer, und mit den eigentlichen Pufferdaten nach Abschluss gibt die Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="b3a73-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3a73-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3a73-137">Requirements</span></span>  
 <span data-ttu-id="b3a73-138">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3a73-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3a73-139">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3a73-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3a73-140">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b3a73-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3a73-141">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3a73-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a73-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3a73-142">See also</span></span>

- [<span data-ttu-id="b3a73-143">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3a73-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b3a73-144">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3a73-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="b3a73-145">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3a73-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
