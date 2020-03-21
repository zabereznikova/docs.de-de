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
ms.openlocfilehash: d8df78e3d5cebe5378dfba11dc0ea93cc8e346eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178100"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="93b94-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="93b94-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>
<span data-ttu-id="93b94-103">Ändert die Bindungsrichtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="93b94-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93b94-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93b94-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="93b94-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="93b94-105">Parameters</span></span>  
 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="93b94-106">[in] Die Identität der zu ändernden Assembly.</span><span class="sxs-lookup"><span data-stu-id="93b94-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="93b94-107">[in] Die neue Identität der geänderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="93b94-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="93b94-108">[in] Ein Zeiger auf einen Puffer, der die Bindungsrichtliniendaten enthält, die die Assembly ändern soll.</span><span class="sxs-lookup"><span data-stu-id="93b94-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="93b94-109">[in] Die Größe der zu ersetzenden Bindungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="93b94-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="93b94-110">[in] Eine logische ODER-Kombination von [EHostBindingPolicyModifyFlags-Werten,](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) die die Steuerung der Umleitung angibt.</span><span class="sxs-lookup"><span data-stu-id="93b94-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="93b94-111">[out] Ein Zeiger auf einen Puffer, der die neuen Bindungsrichtliniendaten enthält.</span><span class="sxs-lookup"><span data-stu-id="93b94-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="93b94-112">[in, out] Ein Zeiger auf die Größe des neuen Bindungsrichtlinienpuffers.</span><span class="sxs-lookup"><span data-stu-id="93b94-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93b94-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="93b94-113">Return Value</span></span>  
  
|<span data-ttu-id="93b94-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93b94-114">HRESULT</span></span>|<span data-ttu-id="93b94-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93b94-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93b94-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="93b94-116">S_OK</span></span>|<span data-ttu-id="93b94-117">Die Richtlinie wurde erfolgreich geändert.</span><span class="sxs-lookup"><span data-stu-id="93b94-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="93b94-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="93b94-118">E_INVALIDARG</span></span>|<span data-ttu-id="93b94-119">`pwzSourceAssemblyIdentity`oder `pwzTargetAssemblyIdentity` war ein Nullverweis.</span><span class="sxs-lookup"><span data-stu-id="93b94-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="93b94-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="93b94-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="93b94-121">`pbNewApplicationPolicy` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="93b94-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="93b94-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="93b94-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="93b94-123">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="93b94-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="93b94-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="93b94-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="93b94-125">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="93b94-125">The call timed out.</span></span>|  
|<span data-ttu-id="93b94-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="93b94-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="93b94-127">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="93b94-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="93b94-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="93b94-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="93b94-129">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="93b94-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="93b94-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="93b94-130">E_FAIL</span></span>|<span data-ttu-id="93b94-131">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="93b94-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="93b94-132">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93b94-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="93b94-133">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="93b94-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93b94-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="93b94-134">Remarks</span></span>  
 <span data-ttu-id="93b94-135">Die `ModifyApplicationPolicy` Methode kann zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="93b94-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="93b94-136">Der erste Aufruf sollte einen `pbNewApplicationPolicy` NULL-Wert für den Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="93b94-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="93b94-137">Dieser Aufruf wird mit dem `pcbNewAppPolicySize`erforderlichen Wert für zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="93b94-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="93b94-138">Der zweite Aufruf sollte `pcbNewAppPolicySize`diesen Wert für bereitstellen und `pbNewApplicationPolicy`auf einen Puffer dieser Größe für verweisen.</span><span class="sxs-lookup"><span data-stu-id="93b94-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93b94-139">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="93b94-139">Requirements</span></span>  
 <span data-ttu-id="93b94-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93b94-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93b94-141">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="93b94-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93b94-142">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="93b94-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93b94-143">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93b94-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b94-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93b94-144">See also</span></span>

- [<span data-ttu-id="93b94-145">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93b94-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
