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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46462362e959b6af9d9b0d311f813e183dfb04df
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474474"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="48aa6-102">ICLRPolicyManager::SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="48aa6-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="48aa6-103">Gibt die Richtlinienaktion, die die common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Vorgang ein auftritt Timeout.</span><span class="sxs-lookup"><span data-stu-id="48aa6-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48aa6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48aa6-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48aa6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48aa6-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="48aa6-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der den Vorgang für die die Timeoutaktion an.</span><span class="sxs-lookup"><span data-stu-id="48aa6-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="48aa6-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="48aa6-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="48aa6-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="48aa6-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="48aa6-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="48aa6-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="48aa6-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="48aa6-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="48aa6-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="48aa6-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="48aa6-112">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die die Richtlinienaktion, die ausgeführt werden, wenn der Vorgang ein auftritt Timeout.</span><span class="sxs-lookup"><span data-stu-id="48aa6-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48aa6-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48aa6-113">Return Value</span></span>  
  
|<span data-ttu-id="48aa6-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48aa6-114">HRESULT</span></span>|<span data-ttu-id="48aa6-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48aa6-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48aa6-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="48aa6-116">S_OK</span></span>|<span data-ttu-id="48aa6-117">`SetActionOnTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48aa6-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="48aa6-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48aa6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48aa6-119">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="48aa6-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48aa6-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48aa6-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48aa6-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48aa6-121">The call timed out.</span></span>|  
|<span data-ttu-id="48aa6-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48aa6-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48aa6-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="48aa6-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48aa6-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48aa6-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48aa6-125">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="48aa6-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48aa6-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48aa6-126">E_FAIL</span></span>|<span data-ttu-id="48aa6-127">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48aa6-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48aa6-128">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48aa6-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48aa6-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="48aa6-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="48aa6-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="48aa6-130">E_INVALIDARG</span></span>|<span data-ttu-id="48aa6-131">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="48aa6-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48aa6-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48aa6-132">Remarks</span></span>  
 <span data-ttu-id="48aa6-133">Der Timeoutwert kann sein, entweder das standardmäßige Timeout, die von der CLR festgelegt oder ein Wert angegeben wird, durch den Host in einem Aufruf der [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="48aa6-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="48aa6-134">Nicht alle Richtlinien Action-Werte können als das Timeoutverhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="48aa6-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="48aa6-135">`SetActionOnTimeout` wird in der Regel nur für die Eskalation von Verhalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="48aa6-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="48aa6-136">Ein Host kann beispielsweise angeben, dass es sich bei Threadabbrüche in grobe umgewandelt werden thread-Abbrüche, aber nicht das Gegenteil angeben.</span><span class="sxs-lookup"><span data-stu-id="48aa6-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="48aa6-137">Die folgende Tabelle beschreibt die gültigen `action` Werte für gültige `operation` Werte.</span><span class="sxs-lookup"><span data-stu-id="48aa6-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="48aa6-138">Wert für `operation`</span><span class="sxs-lookup"><span data-stu-id="48aa6-138">Value for `operation`</span></span>|<span data-ttu-id="48aa6-139">Gültige Werte für `action`</span><span class="sxs-lookup"><span data-stu-id="48aa6-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="48aa6-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="48aa6-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="48aa6-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="48aa6-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="48aa6-142">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="48aa6-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="48aa6-143">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="48aa6-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="48aa6-144">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="48aa6-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="48aa6-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-145">-   eExitProcess</span></span><br /><span data-ttu-id="48aa6-146">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="48aa6-147">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="48aa6-148">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="48aa6-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="48aa6-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="48aa6-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="48aa6-150">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="48aa6-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="48aa6-151">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="48aa6-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="48aa6-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-152">-   eExitProcess</span></span><br /><span data-ttu-id="48aa6-153">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="48aa6-154">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="48aa6-155">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="48aa6-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="48aa6-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="48aa6-156">OPR_ProcessExit</span></span>|<span data-ttu-id="48aa6-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-157">-   eExitProcess</span></span><br /><span data-ttu-id="48aa6-158">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="48aa6-159">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="48aa6-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="48aa6-160">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="48aa6-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48aa6-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48aa6-161">Requirements</span></span>  
 <span data-ttu-id="48aa6-162">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48aa6-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48aa6-163">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48aa6-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48aa6-164">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48aa6-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48aa6-165">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48aa6-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48aa6-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48aa6-166">See also</span></span>
- [<span data-ttu-id="48aa6-167">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="48aa6-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="48aa6-168">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="48aa6-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="48aa6-169">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48aa6-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="48aa6-170">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48aa6-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
