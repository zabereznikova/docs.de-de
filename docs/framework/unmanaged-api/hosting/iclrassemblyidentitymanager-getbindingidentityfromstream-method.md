---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa487ece58f228345188338fb61f1a2a85d9e4c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="3da9e-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="3da9e-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="3da9e-103">Ruft die Identitätsdaten kanonische Assembly für die Assembly im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="3da9e-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3da9e-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3da9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3da9e-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="3da9e-106">[in] Der auszuwertende Assembly-Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="3da9e-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3da9e-107">[in] Für zukünftige Erweiterungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3da9e-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="3da9e-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3da9e-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="3da9e-109">[out] Ein Puffer, der nicht transparenten Assembly Identitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="3da9e-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="3da9e-110">[in, out] Die Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="3da9e-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3da9e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3da9e-111">Return Value</span></span>  
  
|<span data-ttu-id="3da9e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3da9e-112">HRESULT</span></span>|<span data-ttu-id="3da9e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3da9e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3da9e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3da9e-114">S_OK</span></span>|<span data-ttu-id="3da9e-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3da9e-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="3da9e-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3da9e-116">E_INVALIDARG</span></span>|<span data-ttu-id="3da9e-117">Die angegebene `pStream` ist null.</span><span class="sxs-lookup"><span data-stu-id="3da9e-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="3da9e-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="3da9e-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="3da9e-119">Die Größe des `pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="3da9e-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="3da9e-120">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="3da9e-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3da9e-121">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3da9e-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3da9e-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3da9e-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3da9e-123">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3da9e-123">The call timed out.</span></span>|  
|<span data-ttu-id="3da9e-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3da9e-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3da9e-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3da9e-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3da9e-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3da9e-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3da9e-127">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3da9e-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3da9e-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3da9e-128">E_FAIL</span></span>|<span data-ttu-id="3da9e-129">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3da9e-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3da9e-130">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="3da9e-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3da9e-131">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3da9e-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3da9e-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3da9e-132">Requirements</span></span>  
 <span data-ttu-id="3da9e-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3da9e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da9e-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3da9e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3da9e-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3da9e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3da9e-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da9e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da9e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3da9e-137">See Also</span></span>  
 [<span data-ttu-id="3da9e-138">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da9e-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="3da9e-139">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da9e-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
