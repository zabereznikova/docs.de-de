---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd16f13bd77127953bdd17b258c7be518088f899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="dbb82-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="dbb82-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="dbb82-103">Ruft die Identitätsdaten kanonische Assembly für die Assembly im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="dbb82-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbb82-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbb82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbb82-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="dbb82-106">[in] Der auszuwertende Assembly-Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="dbb82-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dbb82-107">[in] Für zukünftige Erweiterungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dbb82-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="dbb82-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dbb82-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="dbb82-109">[out] Ein Puffer, der nicht transparenten Assembly Identitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="dbb82-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="dbb82-110">[in, out] Die Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="dbb82-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbb82-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dbb82-111">Return Value</span></span>  
  
|<span data-ttu-id="dbb82-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbb82-112">HRESULT</span></span>|<span data-ttu-id="dbb82-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbb82-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbb82-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbb82-114">S_OK</span></span>|<span data-ttu-id="dbb82-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dbb82-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="dbb82-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dbb82-116">E_INVALIDARG</span></span>|<span data-ttu-id="dbb82-117">Die angegebene `pStream` ist null.</span><span class="sxs-lookup"><span data-stu-id="dbb82-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="dbb82-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="dbb82-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="dbb82-119">Die Größe des `pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="dbb82-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="dbb82-120">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="dbb82-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dbb82-121">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="dbb82-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dbb82-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dbb82-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dbb82-123">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dbb82-123">The call timed out.</span></span>|  
|<span data-ttu-id="dbb82-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dbb82-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dbb82-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dbb82-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dbb82-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dbb82-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dbb82-127">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="dbb82-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dbb82-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dbb82-128">E_FAIL</span></span>|<span data-ttu-id="dbb82-129">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="dbb82-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dbb82-130">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="dbb82-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dbb82-131">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dbb82-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbb82-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbb82-132">Requirements</span></span>  
 <span data-ttu-id="dbb82-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbb82-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb82-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbb82-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbb82-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dbb82-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbb82-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbb82-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb82-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbb82-137">See Also</span></span>  
 [<span data-ttu-id="dbb82-138">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbb82-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="dbb82-139">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbb82-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
