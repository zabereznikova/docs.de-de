---
title: ICLRPolicyManager::SetActionOnTimeout-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 9ef906ed5e8a6985c084741bf06b683da79c546e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140790"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="9fbea-102">ICLRPolicyManager::SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="9fbea-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="9fbea-103">Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn für den angegebenen Vorgang ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="9fbea-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fbea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fbea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fbea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fbea-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="9fbea-106">in Einer der [eclroperations](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) -Werte, der den Vorgang angibt, für den die Timeout Aktion angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="9fbea-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="9fbea-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9fbea-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="9fbea-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="9fbea-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="9fbea-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="9fbea-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="9fbea-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="9fbea-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="9fbea-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="9fbea-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="9fbea-112">in Einer der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die bei einem Timeout des Vorgangs ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9fbea-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fbea-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9fbea-113">Return Value</span></span>  
  
|<span data-ttu-id="9fbea-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fbea-114">HRESULT</span></span>|<span data-ttu-id="9fbea-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fbea-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9fbea-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fbea-116">S_OK</span></span>|<span data-ttu-id="9fbea-117">`SetActionOnTimeout` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9fbea-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="9fbea-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9fbea-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9fbea-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9fbea-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9fbea-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9fbea-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9fbea-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="9fbea-121">The call timed out.</span></span>|  
|<span data-ttu-id="9fbea-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9fbea-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9fbea-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9fbea-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9fbea-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9fbea-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9fbea-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="9fbea-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9fbea-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9fbea-126">E_FAIL</span></span>|<span data-ttu-id="9fbea-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9fbea-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9fbea-128">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fbea-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9fbea-129">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9fbea-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9fbea-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9fbea-130">E_INVALIDARG</span></span>|<span data-ttu-id="9fbea-131">Für den angegebenen `operation`kann kein Timeout festgelegt werden, oder für `operation`wurde ein ungültiger Wert angegeben.</span><span class="sxs-lookup"><span data-stu-id="9fbea-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fbea-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fbea-132">Remarks</span></span>  
 <span data-ttu-id="9fbea-133">Der Timeout Wert kann entweder das von der CLR festgelegte Standard Timeout oder ein Wert sein, der vom Host in einem Aufrufen der [ICLRPolicyManager:: setTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) -Methode angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9fbea-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="9fbea-134">Nicht alle Richtlinien Aktionswerte können als Timeout Verhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9fbea-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="9fbea-135">`SetActionOnTimeout` wird in der Regel nur zum eskalieren des Verhaltens verwendet.</span><span class="sxs-lookup"><span data-stu-id="9fbea-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="9fbea-136">Beispielsweise kann ein Host angeben, dass Thread Abbrüche in grobe Thread Abbrüche umgewandelt werden, aber nicht das Gegenteil angeben können.</span><span class="sxs-lookup"><span data-stu-id="9fbea-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="9fbea-137">In der folgenden Tabelle werden die gültigen `action` Werte für gültige `operation` Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9fbea-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="9fbea-138">Wert für `operation`</span><span class="sxs-lookup"><span data-stu-id="9fbea-138">Value for `operation`</span></span>|<span data-ttu-id="9fbea-139">Gültige Werte für `action`</span><span class="sxs-lookup"><span data-stu-id="9fbea-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="9fbea-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="9fbea-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="9fbea-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="9fbea-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="9fbea-142">-erudeabortthread</span><span class="sxs-lookup"><span data-stu-id="9fbea-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="9fbea-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9fbea-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="9fbea-144">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="9fbea-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="9fbea-145">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="9fbea-145">-   eExitProcess</span></span><br /><span data-ttu-id="9fbea-146">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="9fbea-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="9fbea-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9fbea-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9fbea-148">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="9fbea-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="9fbea-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="9fbea-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="9fbea-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="9fbea-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="9fbea-151">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="9fbea-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="9fbea-152">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="9fbea-152">-   eExitProcess</span></span><br /><span data-ttu-id="9fbea-153">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="9fbea-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="9fbea-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9fbea-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9fbea-155">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="9fbea-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="9fbea-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="9fbea-156">OPR_ProcessExit</span></span>|<span data-ttu-id="9fbea-157">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="9fbea-157">-   eExitProcess</span></span><br /><span data-ttu-id="9fbea-158">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="9fbea-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="9fbea-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="9fbea-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="9fbea-160">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="9fbea-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fbea-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fbea-161">Requirements</span></span>  
 <span data-ttu-id="9fbea-162">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fbea-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fbea-163">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9fbea-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fbea-164">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9fbea-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fbea-165">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fbea-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbea-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fbea-166">See also</span></span>

- [<span data-ttu-id="9fbea-167">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9fbea-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="9fbea-168">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9fbea-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="9fbea-169">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fbea-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9fbea-170">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fbea-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
