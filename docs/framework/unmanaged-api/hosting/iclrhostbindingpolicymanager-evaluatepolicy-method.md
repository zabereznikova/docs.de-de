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
ms.openlocfilehash: ad7856a9376880f867e35f1e63bc2cac1ca216fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130138"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="4971c-102">ICLRHostBindingPolicyManager::EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="4971c-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="4971c-103">Wertet Richtlinien für die Bindung für den Host.</span><span class="sxs-lookup"><span data-stu-id="4971c-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4971c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4971c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4971c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4971c-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="4971c-106">[in] Ein Verweis auf die Assembly, bevor die richtlinienauswertung.</span><span class="sxs-lookup"><span data-stu-id="4971c-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="4971c-107">[in] Ein Zeiger auf einen Puffer, der die Daten der enthält.</span><span class="sxs-lookup"><span data-stu-id="4971c-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="4971c-108">[in] Die Größe der `pbApplicationPolicy` Puffer.</span><span class="sxs-lookup"><span data-stu-id="4971c-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="4971c-109">[out] Ein Verweis auf die Assembly nach der Auswertung der Daten der neuen.</span><span class="sxs-lookup"><span data-stu-id="4971c-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="4971c-110">[in, out] Ein Zeiger auf die Größe des Puffers Assembly Identität Verweis nach der Auswertung der Daten der neuen.</span><span class="sxs-lookup"><span data-stu-id="4971c-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="4971c-111">[out] Ein Zeiger auf eine logische OR-Kombination von [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) Werte, der angibt, welche Richtlinien angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="4971c-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4971c-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4971c-112">Return Value</span></span>  
  
|<span data-ttu-id="4971c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4971c-113">HRESULT</span></span>|<span data-ttu-id="4971c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4971c-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4971c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4971c-115">S_OK</span></span>|<span data-ttu-id="4971c-116">Die Auswertung wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4971c-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="4971c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4971c-117">E_INVALIDARG</span></span>|<span data-ttu-id="4971c-118">Entweder `pwzReferenceIdentity` oder `pbApplicationPolicy` ist ein null-Verweis.</span><span class="sxs-lookup"><span data-stu-id="4971c-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="4971c-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4971c-119">ERROR_INSUFFICIENT_BUFFER</span></span>|`cbAppPolicySize` <span data-ttu-id="4971c-120">ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="4971c-120">is too small.</span></span>|  
|<span data-ttu-id="4971c-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4971c-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4971c-122">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4971c-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4971c-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4971c-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4971c-124">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4971c-124">The call timed out.</span></span>|  
|<span data-ttu-id="4971c-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4971c-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4971c-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4971c-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4971c-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4971c-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4971c-128">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="4971c-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4971c-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4971c-129">E_FAIL</span></span>|<span data-ttu-id="4971c-130">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4971c-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4971c-131">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4971c-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4971c-132">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4971c-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4971c-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4971c-133">Remarks</span></span>  
 <span data-ttu-id="4971c-134">Die `EvaluatePolicy` Methode ermöglicht es dem Host Bindungsrichtlinie hostspezifische Assembly verwalten beeinflussen Anforderungen an.</span><span class="sxs-lookup"><span data-stu-id="4971c-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="4971c-135">Die Richtlinien-Engine selbst bleibt in der CLR.</span><span class="sxs-lookup"><span data-stu-id="4971c-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4971c-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4971c-136">Requirements</span></span>  
 <span data-ttu-id="4971c-137">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4971c-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4971c-138">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4971c-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4971c-139">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4971c-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4971c-140">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4971c-140">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4971c-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4971c-141">See also</span></span>

- [<span data-ttu-id="4971c-142">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4971c-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
