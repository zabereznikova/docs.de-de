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
ms.openlocfilehash: 8da9c9fea5cf5b3a27eeb9d0222f0845c832b7da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714197"
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a><span data-ttu-id="efc1d-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="efc1d-102">ICLRHostBindingPolicyManager::ModifyApplicationPolicy Method</span></span>

<span data-ttu-id="efc1d-103">Ändert die Bindungs Richtlinie für die angegebene Assembly und erstellt eine neue Version der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="efc1d-103">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efc1d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="efc1d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="efc1d-105">Parameters</span></span>  

 `pwzSourceAssemblyIdentity`  
 <span data-ttu-id="efc1d-106">in Die Identität der Assembly, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="efc1d-106">[in] The identity of the assembly to modify.</span></span>  
  
 `pwzTargetAssemblyIdentity`  
 <span data-ttu-id="efc1d-107">in Die neue Identität der geänderten Assembly.</span><span class="sxs-lookup"><span data-stu-id="efc1d-107">[in] The new identity of the modified assembly.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="efc1d-108">in Ein Zeiger auf einen Puffer, der die Bindungs Richtlinien Daten für die zu ändernde Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="efc1d-108">[in] A pointer to a buffer that contains the binding policy data for the assembly to modify.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="efc1d-109">in Die Größe der zu ersetzenden Bindungs Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="efc1d-109">[in] The size of the binding policy to be replaced.</span></span>  
  
 `dwPolicyModifyFlags`  
 <span data-ttu-id="efc1d-110">in Eine logische OR-Kombination von [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) -Werten, die die Steuerung der Umleitung angeben.</span><span class="sxs-lookup"><span data-stu-id="efc1d-110">[in] A logical OR combination of [EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md) values, indicating control of redirection.</span></span>  
  
 `pbNewApplicationPolicy`  
 <span data-ttu-id="efc1d-111">vorgenommen Ein Zeiger auf einen Puffer, der die neuen Bindungs Richtlinien Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="efc1d-111">[out] A pointer to a buffer that contains the new binding policy data.</span></span>  
  
 `pcbNewAppPolicySize`  
 <span data-ttu-id="efc1d-112">[in, out] Ein Zeiger auf die Größe des neuen Bindungs Richtlinien Puffers.</span><span class="sxs-lookup"><span data-stu-id="efc1d-112">[in, out] A pointer to the size of the new binding policy buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efc1d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="efc1d-113">Return Value</span></span>  
  
|<span data-ttu-id="efc1d-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="efc1d-114">HRESULT</span></span>|<span data-ttu-id="efc1d-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="efc1d-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="efc1d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="efc1d-116">S_OK</span></span>|<span data-ttu-id="efc1d-117">Die Richtlinie wurde erfolgreich geändert.</span><span class="sxs-lookup"><span data-stu-id="efc1d-117">The policy was modified successfully.</span></span>|  
|<span data-ttu-id="efc1d-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="efc1d-118">E_INVALIDARG</span></span>|<span data-ttu-id="efc1d-119">`pwzSourceAssemblyIdentity` oder `pwzTargetAssemblyIdentity` war ein NULL-Verweis.</span><span class="sxs-lookup"><span data-stu-id="efc1d-119">`pwzSourceAssemblyIdentity` or `pwzTargetAssemblyIdentity` was a null reference.</span></span>|  
|<span data-ttu-id="efc1d-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="efc1d-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="efc1d-121">`pbNewApplicationPolicy` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="efc1d-121">`pbNewApplicationPolicy` is too small.</span></span>|  
|<span data-ttu-id="efc1d-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="efc1d-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="efc1d-123">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="efc1d-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="efc1d-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="efc1d-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="efc1d-125">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="efc1d-125">The call timed out.</span></span>|  
|<span data-ttu-id="efc1d-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="efc1d-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="efc1d-127">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="efc1d-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="efc1d-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="efc1d-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="efc1d-129">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="efc1d-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="efc1d-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="efc1d-130">E_FAIL</span></span>|<span data-ttu-id="efc1d-131">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="efc1d-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="efc1d-132">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="efc1d-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="efc1d-133">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="efc1d-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efc1d-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="efc1d-134">Remarks</span></span>  

 <span data-ttu-id="efc1d-135">Die- `ModifyApplicationPolicy` Methode kann zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="efc1d-135">The `ModifyApplicationPolicy` method can be called twice.</span></span> <span data-ttu-id="efc1d-136">Der erste-Befehl sollte einen NULL-Wert für den- `pbNewApplicationPolicy` Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="efc1d-136">The first call should supply a null value for the `pbNewApplicationPolicy` parameter.</span></span> <span data-ttu-id="efc1d-137">Dieser Rückruf gibt mit dem erforderlichen Wert für zurück `pcbNewAppPolicySize` .</span><span class="sxs-lookup"><span data-stu-id="efc1d-137">This call will return with the necessary value for `pcbNewAppPolicySize`.</span></span> <span data-ttu-id="efc1d-138">Der zweite-Befehl sollte diesen Wert für angeben `pcbNewAppPolicySize` und auf einen Puffer dieser Größe für zeigen `pbNewApplicationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="efc1d-138">The second call should supply this value for `pcbNewAppPolicySize`, and point to a buffer of that size for `pbNewApplicationPolicy`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efc1d-139">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="efc1d-139">Requirements</span></span>  

 <span data-ttu-id="efc1d-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efc1d-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efc1d-141">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="efc1d-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="efc1d-142">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="efc1d-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="efc1d-143">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efc1d-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc1d-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efc1d-144">See also</span></span>

- [<span data-ttu-id="efc1d-145">ICLRHostBindingPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efc1d-145">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
