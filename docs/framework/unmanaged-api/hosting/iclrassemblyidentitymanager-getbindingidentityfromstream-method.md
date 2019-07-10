---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16cb3495bbc2fa9ead25afd5e7120774b021a37f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773558"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="40049-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="40049-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="40049-103">Ruft die kanonische Assemblyidentitätsdaten für die Assembly im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="40049-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40049-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40049-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40049-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40049-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="40049-106">[in] Der Assemblystream,, die ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="40049-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="40049-107">[in] Für eine zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="40049-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="40049-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="40049-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="40049-109">[out] Ein Puffer mit nicht transparenten Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="40049-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="40049-110">[in, out] Die Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="40049-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40049-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40049-111">Return Value</span></span>  
  
|<span data-ttu-id="40049-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40049-112">HRESULT</span></span>|<span data-ttu-id="40049-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40049-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40049-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="40049-114">S_OK</span></span>|<span data-ttu-id="40049-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40049-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="40049-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="40049-116">E_INVALIDARG</span></span>|<span data-ttu-id="40049-117">Die angegebene `pStream` ist null.</span><span class="sxs-lookup"><span data-stu-id="40049-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="40049-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="40049-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="40049-119">Die Größe des `pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="40049-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="40049-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40049-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40049-121">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="40049-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40049-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40049-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40049-123">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="40049-123">The call timed out.</span></span>|  
|<span data-ttu-id="40049-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40049-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40049-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="40049-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40049-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40049-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40049-127">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="40049-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40049-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40049-128">E_FAIL</span></span>|<span data-ttu-id="40049-129">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="40049-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40049-130">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40049-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40049-131">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="40049-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40049-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40049-132">Requirements</span></span>  
 <span data-ttu-id="40049-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40049-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40049-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40049-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40049-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="40049-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40049-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40049-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40049-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40049-137">See also</span></span>

- [<span data-ttu-id="40049-138">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40049-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="40049-139">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40049-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
