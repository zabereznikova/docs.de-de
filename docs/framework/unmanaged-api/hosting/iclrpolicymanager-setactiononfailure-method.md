---
title: ICLRPolicyManager::SetActionOnFailure-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4440b36485ed900b5e64adcead2525dbb7d5206e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="04483-102">ICLRPolicyManager::SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="04483-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="04483-103">Gibt die Richtlinienaktion, die die common Language Runtime (CLR) ausführen sollten, wenn der angegebene Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="04483-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04483-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="04483-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04483-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="04483-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="04483-106">[in] Eines der [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) Werte, der den Typ des Fehlers für die Aktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="04483-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="04483-107">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der die Aktion, die ausgeführt werden, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="04483-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="04483-108">Eine Liste der unterstützten Werten finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="04483-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04483-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="04483-109">Return Value</span></span>  
  
|<span data-ttu-id="04483-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04483-110">HRESULT</span></span>|<span data-ttu-id="04483-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04483-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04483-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="04483-112">S_OK</span></span>|<span data-ttu-id="04483-113">`SetActionOnFailure`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="04483-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="04483-114">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="04483-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04483-115">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="04483-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04483-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04483-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04483-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="04483-117">The call timed out.</span></span>|  
|<span data-ttu-id="04483-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04483-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04483-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="04483-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04483-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04483-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04483-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="04483-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04483-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04483-122">E_FAIL</span></span>|<span data-ttu-id="04483-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="04483-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04483-124">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="04483-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04483-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="04483-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="04483-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="04483-126">E_INVALIDARG</span></span>|<span data-ttu-id="04483-127">Eine Richtlinienaktion kann nicht festgelegt werden, für den angegebenen Vorgang, oder eine ungültige Richtlinie für den Vorgang angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="04483-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04483-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="04483-128">Remarks</span></span>  
 <span data-ttu-id="04483-129">Standardmäßig löst die CLR eine Ausnahme aus, wenn ein Fehler auftritt, eine Ressource, z. B. Arbeitsspeicher reservieren.</span><span class="sxs-lookup"><span data-stu-id="04483-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="04483-130">`SetActionOnFailure`ermöglicht es dem Host auf dieses Verhalten überschreiben, indem Sie die auszuführende Richtlinienaktion bei einem Fehler angeben.</span><span class="sxs-lookup"><span data-stu-id="04483-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="04483-131">Die folgende Tabelle zeigt die Kombinationen von [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) und [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="04483-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="04483-132">(Das Präfix FAIL_ fehlt [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) Werte.)</span><span class="sxs-lookup"><span data-stu-id="04483-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="04483-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="04483-133">NonCriticalResource</span></span>|<span data-ttu-id="04483-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="04483-134">CriticalResource</span></span>|<span data-ttu-id="04483-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="04483-135">FatalRuntime</span></span>|<span data-ttu-id="04483-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="04483-136">OrphanedLock</span></span>|<span data-ttu-id="04483-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="04483-137">StackOverflow</span></span>|<span data-ttu-id="04483-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="04483-138">AccessViolation</span></span>|<span data-ttu-id="04483-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="04483-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="04483-140">X</span><span class="sxs-lookup"><span data-stu-id="04483-140">X</span></span>|<span data-ttu-id="04483-141">X</span><span class="sxs-lookup"><span data-stu-id="04483-141">X</span></span>||||<span data-ttu-id="04483-142">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-142">N/A</span></span>||  
|<span data-ttu-id="04483-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="04483-143">eThrowException</span></span>|<span data-ttu-id="04483-144">X</span><span class="sxs-lookup"><span data-stu-id="04483-144">X</span></span>|<span data-ttu-id="04483-145">X</span><span class="sxs-lookup"><span data-stu-id="04483-145">X</span></span>||||<span data-ttu-id="04483-146">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="04483-147">X</span><span class="sxs-lookup"><span data-stu-id="04483-147">X</span></span>|<span data-ttu-id="04483-148">X</span><span class="sxs-lookup"><span data-stu-id="04483-148">X</span></span>||||<span data-ttu-id="04483-149">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-149">N/A</span></span>|<span data-ttu-id="04483-150">X</span><span class="sxs-lookup"><span data-stu-id="04483-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="04483-151">X</span><span class="sxs-lookup"><span data-stu-id="04483-151">X</span></span>|<span data-ttu-id="04483-152">X</span><span class="sxs-lookup"><span data-stu-id="04483-152">X</span></span>||||<span data-ttu-id="04483-153">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-153">N/A</span></span>|<span data-ttu-id="04483-154">X</span><span class="sxs-lookup"><span data-stu-id="04483-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="04483-155">X</span><span class="sxs-lookup"><span data-stu-id="04483-155">X</span></span>|<span data-ttu-id="04483-156">X</span><span class="sxs-lookup"><span data-stu-id="04483-156">X</span></span>||<span data-ttu-id="04483-157">X</span><span class="sxs-lookup"><span data-stu-id="04483-157">X</span></span>||<span data-ttu-id="04483-158">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-158">N/A</span></span>|<span data-ttu-id="04483-159">X</span><span class="sxs-lookup"><span data-stu-id="04483-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="04483-160">X</span><span class="sxs-lookup"><span data-stu-id="04483-160">X</span></span>|<span data-ttu-id="04483-161">X</span><span class="sxs-lookup"><span data-stu-id="04483-161">X</span></span>||<span data-ttu-id="04483-162">X</span><span class="sxs-lookup"><span data-stu-id="04483-162">X</span></span>|<span data-ttu-id="04483-163">X</span><span class="sxs-lookup"><span data-stu-id="04483-163">X</span></span>|<span data-ttu-id="04483-164">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-164">N/A</span></span>|<span data-ttu-id="04483-165">X</span><span class="sxs-lookup"><span data-stu-id="04483-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="04483-166">X</span><span class="sxs-lookup"><span data-stu-id="04483-166">X</span></span>|<span data-ttu-id="04483-167">X</span><span class="sxs-lookup"><span data-stu-id="04483-167">X</span></span>||<span data-ttu-id="04483-168">X</span><span class="sxs-lookup"><span data-stu-id="04483-168">X</span></span>|<span data-ttu-id="04483-169">X</span><span class="sxs-lookup"><span data-stu-id="04483-169">X</span></span>|<span data-ttu-id="04483-170">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-170">N/A</span></span>|<span data-ttu-id="04483-171">X</span><span class="sxs-lookup"><span data-stu-id="04483-171">X</span></span>|  
|<span data-ttu-id="04483-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="04483-172">eFastExitProcess</span></span>|<span data-ttu-id="04483-173">X</span><span class="sxs-lookup"><span data-stu-id="04483-173">X</span></span>|<span data-ttu-id="04483-174">X</span><span class="sxs-lookup"><span data-stu-id="04483-174">X</span></span>||<span data-ttu-id="04483-175">X</span><span class="sxs-lookup"><span data-stu-id="04483-175">X</span></span>|<span data-ttu-id="04483-176">X</span><span class="sxs-lookup"><span data-stu-id="04483-176">X</span></span>|<span data-ttu-id="04483-177">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="04483-178">X</span><span class="sxs-lookup"><span data-stu-id="04483-178">X</span></span>|<span data-ttu-id="04483-179">X</span><span class="sxs-lookup"><span data-stu-id="04483-179">X</span></span>|<span data-ttu-id="04483-180">X</span><span class="sxs-lookup"><span data-stu-id="04483-180">X</span></span>|<span data-ttu-id="04483-181">X</span><span class="sxs-lookup"><span data-stu-id="04483-181">X</span></span>|<span data-ttu-id="04483-182">X</span><span class="sxs-lookup"><span data-stu-id="04483-182">X</span></span>|<span data-ttu-id="04483-183">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="04483-184">X</span><span class="sxs-lookup"><span data-stu-id="04483-184">X</span></span>|<span data-ttu-id="04483-185">X</span><span class="sxs-lookup"><span data-stu-id="04483-185">X</span></span>|<span data-ttu-id="04483-186">X</span><span class="sxs-lookup"><span data-stu-id="04483-186">X</span></span>|<span data-ttu-id="04483-187">X</span><span class="sxs-lookup"><span data-stu-id="04483-187">X</span></span>|<span data-ttu-id="04483-188">X</span><span class="sxs-lookup"><span data-stu-id="04483-188">X</span></span>|<span data-ttu-id="04483-189">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="04483-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="04483-190">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04483-190">Requirements</span></span>  
 <span data-ttu-id="04483-191">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04483-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04483-192">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="04483-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04483-193">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="04483-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04483-194">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04483-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04483-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04483-195">See Also</span></span>  
 [<span data-ttu-id="04483-196">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="04483-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="04483-197">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="04483-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="04483-198">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04483-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="04483-199">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04483-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
