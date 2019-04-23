---
title: ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07a4998f86958e21fffc8ba8657ec9f2a170f43e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112436"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="05aaf-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="05aaf-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="05aaf-103">Ändert die Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="05aaf-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05aaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05aaf-104">Syntax</span></span>  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05aaf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05aaf-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="05aaf-106">[in] Die Identität der Assembly, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="05aaf-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="05aaf-107">[in] Die neue Identität der Assembly geändert.</span><span class="sxs-lookup"><span data-stu-id="05aaf-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="05aaf-108">[in] Ein Zeiger auf einen Puffer, der Daten der Bindung für den zu ändernden Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="05aaf-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="05aaf-109">[in] Die Größe der Bindungsrichtlinie ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="05aaf-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="05aaf-110">[in] Eine logische OR-Kombination von [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) Werte, der Kontrolle über die Umleitung angibt.</span><span class="sxs-lookup"><span data-stu-id="05aaf-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="05aaf-111">[out] Ein Zeiger auf einen Puffer, der Daten der neuen Bindung enthält.</span><span class="sxs-lookup"><span data-stu-id="05aaf-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="05aaf-112">[in, out] Ein Zeiger auf die Größe des Puffers Richtlinie neue Bindung.</span><span class="sxs-lookup"><span data-stu-id="05aaf-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05aaf-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05aaf-113">Return Value</span></span>  
  
|<span data-ttu-id="05aaf-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05aaf-114">HRESULT</span></span>|<span data-ttu-id="05aaf-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05aaf-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05aaf-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="05aaf-116">S_OK</span></span>|<span data-ttu-id="05aaf-117">Die Richtlinie wurde erfolgreich geändert.</span><span class="sxs-lookup"><span data-stu-id="05aaf-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="05aaf-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="05aaf-118">E_INVALIDARG</span></span>|<span data-ttu-id="05aaf-119">`pwzSourceAssemblyIdentity` oder `pwzTargetAssemblyIdentity` wurde ein null-Verweis.</span><span class="sxs-lookup"><span data-stu-id="05aaf-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="05aaf-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="05aaf-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="05aaf-121">`pbNewApplicationPolicy` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="05aaf-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="05aaf-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="05aaf-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="05aaf-123">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="05aaf-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="05aaf-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="05aaf-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="05aaf-125">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="05aaf-125">The call timed out.</span></span>|  
|<span data-ttu-id="05aaf-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="05aaf-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="05aaf-127">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="05aaf-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="05aaf-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="05aaf-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="05aaf-129">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="05aaf-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="05aaf-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="05aaf-130">E_FAIL</span></span>|<span data-ttu-id="05aaf-131">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="05aaf-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="05aaf-132">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05aaf-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="05aaf-133">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="05aaf-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05aaf-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05aaf-134">Remarks</span></span>  
 <span data-ttu-id="05aaf-135">Die `ModifyApplicationPolicy` -Methode zweimal aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="05aaf-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="05aaf-136">Geben Sie beim erste Aufruf sollte null-Wert für die `pbNewApplicationPolicy` Parameter.</span><span class="sxs-lookup"><span data-stu-id="05aaf-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="05aaf-137">Dieser Aufruf gibt den erforderlichen Wert für `pcbNewAppPolicySize`.</span><span class="sxs-lookup"><span data-stu-id="05aaf-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="05aaf-138">Der zweite Aufruf sollte diesen Wert für bereitstellen `pcbNewAppPolicySize`, und zeigen Sie auf einen Puffer dieser Größe für `pbNewApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="05aaf-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05aaf-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05aaf-139">Requirements</span></span>  
 <span data-ttu-id="05aaf-140">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05aaf-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05aaf-141">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05aaf-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05aaf-142">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="05aaf-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05aaf-143">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05aaf-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05aaf-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05aaf-144">See also</span></span>

- [<span data-ttu-id="05aaf-145">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05aaf-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
