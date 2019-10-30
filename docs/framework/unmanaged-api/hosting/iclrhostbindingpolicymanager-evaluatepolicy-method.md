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
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141179"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="f43bf-102">ICLRHostBindingPolicyManager::EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="f43bf-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="f43bf-103">Wertet die Bindungs Richtlinie im Namen des Hosts aus.</span><span class="sxs-lookup"><span data-stu-id="f43bf-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f43bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f43bf-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f43bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f43bf-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="f43bf-106">in Ein Verweis auf die Assembly vor der Richtlinien Auswertung.</span><span class="sxs-lookup"><span data-stu-id="f43bf-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="f43bf-107">in Ein Zeiger auf einen Puffer, der die Richtlinien Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="f43bf-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="f43bf-108">in Die Größe des `pbApplicationPolicy` Puffers.</span><span class="sxs-lookup"><span data-stu-id="f43bf-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="f43bf-109">vorgenommen Ein Verweis auf die Assembly nach der Auswertung der neuen Richtlinien Daten.</span><span class="sxs-lookup"><span data-stu-id="f43bf-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="f43bf-110">[in, out] Ein Zeiger auf die Größe des assemblyidentitätsverweispuffers nach der Auswertung der neuen Richtlinien Daten.</span><span class="sxs-lookup"><span data-stu-id="f43bf-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="f43bf-111">vorgenommen Ein Zeiger auf eine logische OR-Kombination von [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) -Werten, die angibt, welche Richtlinien angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f43bf-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f43bf-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f43bf-112">Return Value</span></span>  
  
|<span data-ttu-id="f43bf-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f43bf-113">HRESULT</span></span>|<span data-ttu-id="f43bf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f43bf-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f43bf-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f43bf-115">S_OK</span></span>|<span data-ttu-id="f43bf-116">Die Auswertung wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f43bf-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="f43bf-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f43bf-117">E_INVALIDARG</span></span>|<span data-ttu-id="f43bf-118">Entweder `pwzReferenceIdentity` oder `pbApplicationPolicy` ist ein NULL-Verweis.</span><span class="sxs-lookup"><span data-stu-id="f43bf-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="f43bf-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f43bf-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f43bf-120">`cbAppPolicySize` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="f43bf-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="f43bf-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f43bf-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f43bf-122">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f43bf-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f43bf-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f43bf-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f43bf-124">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f43bf-124">The call timed out.</span></span>|  
|<span data-ttu-id="f43bf-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f43bf-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f43bf-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f43bf-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f43bf-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f43bf-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f43bf-128">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f43bf-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f43bf-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f43bf-129">E_FAIL</span></span>|<span data-ttu-id="f43bf-130">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f43bf-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f43bf-131">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f43bf-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f43bf-132">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f43bf-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f43bf-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f43bf-133">Remarks</span></span>  
 <span data-ttu-id="f43bf-134">Mit der `EvaluatePolicy`-Methode kann der Host die Bindungs Richtlinie so beeinflussen, dass Host spezifische assemblyversionsanforderungen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f43bf-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="f43bf-135">Die Richtlinien-Engine selbst verbleibt innerhalb der CLR.</span><span class="sxs-lookup"><span data-stu-id="f43bf-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f43bf-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f43bf-136">Requirements</span></span>  
 <span data-ttu-id="f43bf-137">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f43bf-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f43bf-138">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f43bf-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f43bf-139">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f43bf-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f43bf-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f43bf-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43bf-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f43bf-141">See also</span></span>

- [<span data-ttu-id="f43bf-142">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f43bf-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
