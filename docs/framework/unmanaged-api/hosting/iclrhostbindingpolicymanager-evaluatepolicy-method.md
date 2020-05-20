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
ms.openlocfilehash: f72a66354bfc907dab7ebc24de515bdfb20ddfb2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703598"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="cfc4e-102">ICLRHostBindingPolicyManager::EvaluatePolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="cfc4e-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="cfc4e-103">Wertet die Bindungs Richtlinie im Namen des Hosts aus.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfc4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfc4e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cfc4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfc4e-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="cfc4e-106">in Ein Verweis auf die Assembly vor der Richtlinien Auswertung.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="cfc4e-107">in Ein Zeiger auf einen Puffer, der die Richtlinien Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="cfc4e-108">in Die Größe des `pbApplicationPolicy` Puffers.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="cfc4e-109">vorgenommen Ein Verweis auf die Assembly nach der Auswertung der neuen Richtlinien Daten.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="cfc4e-110">[in, out] Ein Zeiger auf die Größe des assemblyidentitätsverweispuffers nach der Auswertung der neuen Richtlinien Daten.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="cfc4e-111">vorgenommen Ein Zeiger auf eine logische OR-Kombination von [EBindPolicyLevels](ebindpolicylevels-enumeration.md) -Werten, die angibt, welche Richtlinien angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfc4e-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cfc4e-112">Return Value</span></span>  
  
|<span data-ttu-id="cfc4e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cfc4e-113">HRESULT</span></span>|<span data-ttu-id="cfc4e-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cfc4e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfc4e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="cfc4e-115">S_OK</span></span>|<span data-ttu-id="cfc4e-116">Die Auswertung wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="cfc4e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cfc4e-117">E_INVALIDARG</span></span>|<span data-ttu-id="cfc4e-118">Entweder `pwzReferenceIdentity` oder `pbApplicationPolicy` ist ein NULL-Verweis.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="cfc4e-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="cfc4e-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="cfc4e-120">`cbAppPolicySize` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="cfc4e-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cfc4e-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cfc4e-122">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cfc4e-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cfc4e-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cfc4e-124">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-124">The call timed out.</span></span>|  
|<span data-ttu-id="cfc4e-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cfc4e-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cfc4e-126">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cfc4e-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cfc4e-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cfc4e-128">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cfc4e-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cfc4e-129">E_FAIL</span></span>|<span data-ttu-id="cfc4e-130">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cfc4e-131">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cfc4e-132">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfc4e-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfc4e-133">Remarks</span></span>  
 <span data-ttu-id="cfc4e-134">Die- `EvaluatePolicy` Methode ermöglicht es dem Host, die Bindungs Richtlinie zu beeinflussen, um Host spezifische assemblyversionsanforderungen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="cfc4e-135">Die Richtlinien-Engine selbst verbleibt innerhalb der CLR.</span><span class="sxs-lookup"><span data-stu-id="cfc4e-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfc4e-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfc4e-136">Requirements</span></span>  
 <span data-ttu-id="cfc4e-137">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfc4e-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfc4e-138">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cfc4e-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfc4e-139">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cfc4e-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfc4e-140">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfc4e-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc4e-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfc4e-141">See also</span></span>

- [<span data-ttu-id="cfc4e-142">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfc4e-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
