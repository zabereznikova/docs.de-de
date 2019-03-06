---
title: ICLRHostBindingPolicyManager::EvaluatePolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3310f584475a4d6a6f0e3e790db13875faf60cf2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466686"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="9936d-102">ICLRHostBindingPolicyManager::EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="9936d-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="9936d-103">Wertet Richtlinien für die Bindung für den Host.</span><span class="sxs-lookup"><span data-stu-id="9936d-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9936d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9936d-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9936d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9936d-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="9936d-106">[in] Ein Verweis auf die Assembly, bevor die richtlinienauswertung.</span><span class="sxs-lookup"><span data-stu-id="9936d-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="9936d-107">[in] Ein Zeiger auf einen Puffer, der die Daten der enthält.</span><span class="sxs-lookup"><span data-stu-id="9936d-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="9936d-108">[in] Die Größe der `pbApplicationPolicy` Puffer.</span><span class="sxs-lookup"><span data-stu-id="9936d-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="9936d-109">[out] Ein Verweis auf die Assembly nach der Auswertung der Daten der neuen.</span><span class="sxs-lookup"><span data-stu-id="9936d-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="9936d-110">[in, out] Ein Zeiger auf die Größe des Puffers Assembly Identität Verweis nach der Auswertung der Daten der neuen.</span><span class="sxs-lookup"><span data-stu-id="9936d-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="9936d-111">[out] Ein Zeiger auf eine logische OR-Kombination von [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) Werte, der angibt, welche Richtlinien angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9936d-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9936d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9936d-112">Return Value</span></span>  
  
|<span data-ttu-id="9936d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9936d-113">HRESULT</span></span>|<span data-ttu-id="9936d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9936d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9936d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9936d-115">S_OK</span></span>|<span data-ttu-id="9936d-116">Die Auswertung wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9936d-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="9936d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9936d-117">E_INVALIDARG</span></span>|<span data-ttu-id="9936d-118">Entweder `pwzReferenceIdentity` oder `pbApplicationPolicy` ist ein null-Verweis.</span><span class="sxs-lookup"><span data-stu-id="9936d-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="9936d-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9936d-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9936d-120">`cbAppPolicySize` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="9936d-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="9936d-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9936d-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9936d-122">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9936d-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9936d-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9936d-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9936d-124">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9936d-124">The call timed out.</span></span>|  
|<span data-ttu-id="9936d-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9936d-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9936d-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9936d-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9936d-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9936d-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9936d-128">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9936d-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9936d-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9936d-129">E_FAIL</span></span>|<span data-ttu-id="9936d-130">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9936d-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9936d-131">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9936d-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9936d-132">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9936d-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9936d-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9936d-133">Remarks</span></span>  
 <span data-ttu-id="9936d-134">Die `EvaluatePolicy` Methode ermöglicht es dem Host Bindungsrichtlinie hostspezifische Assembly verwalten beeinflussen Anforderungen an.</span><span class="sxs-lookup"><span data-stu-id="9936d-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="9936d-135">Die Richtlinien-Engine selbst bleibt in der CLR.</span><span class="sxs-lookup"><span data-stu-id="9936d-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9936d-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9936d-136">Requirements</span></span>  
 <span data-ttu-id="9936d-137">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9936d-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9936d-138">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9936d-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9936d-139">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9936d-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9936d-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9936d-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9936d-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9936d-141">See also</span></span>
- [<span data-ttu-id="9936d-142">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9936d-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
