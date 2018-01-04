---
title: ICLRPolicyManager::SetActionOnTimeout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnTimeout
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db0918272a315e78191624cbe6420863285620c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="0ce63-102">ICLRPolicyManager::SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="0ce63-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="0ce63-103">Gibt die Richtlinienaktion, die die common Language Runtime (CLR) ausführen sollten, wenn der angegebene Vorgang ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="0ce63-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ce63-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ce63-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ce63-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="0ce63-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der den Vorgang für die die Timeoutaktion an.</span><span class="sxs-lookup"><span data-stu-id="0ce63-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="0ce63-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0ce63-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0ce63-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="0ce63-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="0ce63-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="0ce63-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="0ce63-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="0ce63-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="0ce63-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="0ce63-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="0ce63-112">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der die Richtlinienaktion, die ausgeführt werden, wenn der Vorgang ein Timeout eintritt.</span><span class="sxs-lookup"><span data-stu-id="0ce63-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ce63-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ce63-113">Return Value</span></span>  
  
|<span data-ttu-id="0ce63-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ce63-114">HRESULT</span></span>|<span data-ttu-id="0ce63-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ce63-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ce63-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ce63-116">S_OK</span></span>|<span data-ttu-id="0ce63-117">`SetActionOnTimeout`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ce63-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="0ce63-118">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="0ce63-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ce63-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0ce63-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ce63-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ce63-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ce63-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0ce63-121">The call timed out.</span></span>|  
|<span data-ttu-id="0ce63-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ce63-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ce63-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0ce63-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ce63-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ce63-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ce63-125">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0ce63-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ce63-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ce63-126">E_FAIL</span></span>|<span data-ttu-id="0ce63-127">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0ce63-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ce63-128">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="0ce63-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ce63-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0ce63-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0ce63-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0ce63-130">E_INVALIDARG</span></span>|<span data-ttu-id="0ce63-131">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="0ce63-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ce63-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ce63-132">Remarks</span></span>  
 <span data-ttu-id="0ce63-133">Der Timeoutwert kann sein, das von der CLR festgelegte Standardtimeout oder eines Werts durch den Host in einem Aufruf angegeben die [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0ce63-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="0ce63-134">Nicht alle Werte für Aktivierungsrichtlinien Aktion können als das Timeoutverhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0ce63-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="0ce63-135">`SetActionOnTimeout`wird normalerweise verwendet, nur für das Verhalten zu eskalieren.</span><span class="sxs-lookup"><span data-stu-id="0ce63-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="0ce63-136">Ein Host kann z. B. angeben, die Threadabbrüche in grobe aktiviert werden thread-Abbrüche, jedoch nicht das Gegenteil.</span><span class="sxs-lookup"><span data-stu-id="0ce63-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="0ce63-137">Die folgende Tabelle beschreibt die gültigen `action` Werte für gültige `operation` Werte.</span><span class="sxs-lookup"><span data-stu-id="0ce63-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="0ce63-138">Wert für`operation`</span><span class="sxs-lookup"><span data-stu-id="0ce63-138">Value for `operation`</span></span>|<span data-ttu-id="0ce63-139">Gültige Werte für`action`</span><span class="sxs-lookup"><span data-stu-id="0ce63-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="0ce63-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="0ce63-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="0ce63-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="0ce63-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="0ce63-142">-eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="0ce63-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="0ce63-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="0ce63-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="0ce63-144">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="0ce63-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="0ce63-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-145">-   eExitProcess</span></span><br /><span data-ttu-id="0ce63-146">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="0ce63-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="0ce63-148">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="0ce63-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="0ce63-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="0ce63-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="0ce63-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="0ce63-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="0ce63-151">-eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="0ce63-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="0ce63-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-152">-   eExitProcess</span></span><br /><span data-ttu-id="0ce63-153">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="0ce63-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="0ce63-155">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="0ce63-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="0ce63-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="0ce63-156">OPR_ProcessExit</span></span>|<span data-ttu-id="0ce63-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-157">-   eExitProcess</span></span><br /><span data-ttu-id="0ce63-158">-eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="0ce63-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="0ce63-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="0ce63-160">-eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="0ce63-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ce63-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ce63-161">Requirements</span></span>  
 <span data-ttu-id="0ce63-162">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ce63-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ce63-163">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ce63-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ce63-164">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0ce63-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ce63-165">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ce63-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce63-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ce63-166">See Also</span></span>  
 [<span data-ttu-id="0ce63-167">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0ce63-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="0ce63-168">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0ce63-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="0ce63-169">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ce63-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="0ce63-170">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ce63-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
