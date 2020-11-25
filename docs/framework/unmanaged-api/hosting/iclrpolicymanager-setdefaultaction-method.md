---
title: ICLRPolicyManager::SetDefaultAction-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: 93070690ea6b30b22949953f1ed0b8c5b1e92764
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732476"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a><span data-ttu-id="8b8f6-102">ICLRPolicyManager::SetDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="8b8f6-102">ICLRPolicyManager::SetDefaultAction Method</span></span>

<span data-ttu-id="8b8f6-103">Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Vorgang auftritt.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b8f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b8f6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b8f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b8f6-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="8b8f6-106">in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der die Aktion angibt, für die das CLR-Verhalten angepasst werden soll.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the action for which CLR behavior should be customized.</span></span>  
  
 `action`  
 <span data-ttu-id="8b8f6-107">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die die CLR bei Auftreten durchführen soll `operation` .</span><span class="sxs-lookup"><span data-stu-id="8b8f6-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b8f6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8b8f6-108">Return Value</span></span>  
  
|<span data-ttu-id="8b8f6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b8f6-109">HRESULT</span></span>|<span data-ttu-id="8b8f6-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8b8f6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b8f6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b8f6-111">S_OK</span></span>|<span data-ttu-id="8b8f6-112">`SetDefaultAction` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-112">`SetDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="8b8f6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b8f6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b8f6-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b8f6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b8f6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b8f6-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-116">The call timed out.</span></span>|  
|<span data-ttu-id="8b8f6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b8f6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b8f6-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b8f6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b8f6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b8f6-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8b8f6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b8f6-121">E_FAIL</span></span>|<span data-ttu-id="8b8f6-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b8f6-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b8f6-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8b8f6-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8b8f6-125">E_INVALIDARG</span></span>|<span data-ttu-id="8b8f6-126">`action`Für das wurde ein ungültiges angegeben `operation` , oder für wurde ein ungültiger Wert angegeben `operation` .</span><span class="sxs-lookup"><span data-stu-id="8b8f6-126">An invalid `action` was specified for the `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b8f6-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b8f6-127">Remarks</span></span>  

 <span data-ttu-id="8b8f6-128">Nicht alle Richtlinien Aktionswerte können als Standardverhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-128">Not all policy action values can be specified as the default behavior for CLR operations.</span></span> <span data-ttu-id="8b8f6-129">`SetDefaultAction` kann in der Regel nur zum eskalieren des Verhaltens verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-129">`SetDefaultAction` can typically be used only to escalate behavior.</span></span> <span data-ttu-id="8b8f6-130">Beispielsweise kann ein Host angeben, dass Thread Abbrüche in grobe Thread Abbrüche umgewandelt werden, aber nicht das Gegenteil angeben können.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-130">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="8b8f6-131">In der folgenden Tabelle werden die gültigen `action` Werte für die einzelnen möglichen Werte beschrieben `operation` .</span><span class="sxs-lookup"><span data-stu-id="8b8f6-131">The table below describes the valid `action` values for each possible `operation` value.</span></span>  
  
|<span data-ttu-id="8b8f6-132">Wert für `operation`</span><span class="sxs-lookup"><span data-stu-id="8b8f6-132">Value for `operation`</span></span>|<span data-ttu-id="8b8f6-133">Gültige Werte für `action`</span><span class="sxs-lookup"><span data-stu-id="8b8f6-133">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="8b8f6-134">OPR_ThreadAbort</span><span class="sxs-lookup"><span data-stu-id="8b8f6-134">OPR_ThreadAbort</span></span>|<span data-ttu-id="8b8f6-135">-eabortthread</span><span class="sxs-lookup"><span data-stu-id="8b8f6-135">-   eAbortThread</span></span><br /><span data-ttu-id="8b8f6-136">-erudeabortthread</span><span class="sxs-lookup"><span data-stu-id="8b8f6-136">-   eRudeAbortThread</span></span><br /><span data-ttu-id="8b8f6-137">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-137">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-138">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-138">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-139">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-139">-   eExitProcess</span></span><br /><span data-ttu-id="8b8f6-140">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-140">-   eFastExitProcess</span></span><br /><span data-ttu-id="8b8f6-141">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-141">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8b8f6-142">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="8b8f6-142">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8b8f6-143">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8b8f6-143">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="8b8f6-144">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8b8f6-144">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="8b8f6-145">-erudeabortthread</span><span class="sxs-lookup"><span data-stu-id="8b8f6-145">-   eRudeAbortThread</span></span><br /><span data-ttu-id="8b8f6-146">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-146">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-147">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-147">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-148">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-148">-   eExitProcess</span></span><br /><span data-ttu-id="8b8f6-149">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-149">-   eFastExitProcess</span></span><br /><span data-ttu-id="8b8f6-150">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-150">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8b8f6-151">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="8b8f6-151">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8b8f6-152">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="8b8f6-152">OPR_AppDomainUnload</span></span>|<span data-ttu-id="8b8f6-153">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-153">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-154">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-154">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-155">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-155">-   eExitProcess</span></span><br /><span data-ttu-id="8b8f6-156">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-156">-   eFastExitProcess</span></span><br /><span data-ttu-id="8b8f6-157">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-157">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8b8f6-158">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="8b8f6-158">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8b8f6-159">OPR_AppDomainRudeUnload</span><span class="sxs-lookup"><span data-stu-id="8b8f6-159">OPR_AppDomainRudeUnload</span></span>|<span data-ttu-id="8b8f6-160">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-160">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-161">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-161">-   eExitProcess</span></span><br /><span data-ttu-id="8b8f6-162">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-162">-   eFastExitProcess</span></span><br /><span data-ttu-id="8b8f6-163">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-163">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8b8f6-164">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="8b8f6-164">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8b8f6-165">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="8b8f6-165">OPR_ProcessExit</span></span>|<span data-ttu-id="8b8f6-166">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-166">-   eExitProcess</span></span><br /><span data-ttu-id="8b8f6-167">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-167">-   eFastExitProcess</span></span><br /><span data-ttu-id="8b8f6-168">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-168">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8b8f6-169">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="8b8f6-169">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="8b8f6-170">OPR_FinalizerRun</span><span class="sxs-lookup"><span data-stu-id="8b8f6-170">OPR_FinalizerRun</span></span>|<span data-ttu-id="8b8f6-171">-enoaction</span><span class="sxs-lookup"><span data-stu-id="8b8f6-171">-   eNoAction</span></span><br /><span data-ttu-id="8b8f6-172">-eabortthread</span><span class="sxs-lookup"><span data-stu-id="8b8f6-172">-   eAbortThread</span></span><br /><span data-ttu-id="8b8f6-173">-erudeabortthread</span><span class="sxs-lookup"><span data-stu-id="8b8f6-173">-   eRudeAbortThread</span></span><br /><span data-ttu-id="8b8f6-174">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-174">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-175">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="8b8f6-175">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="8b8f6-176">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-176">-   eExitProcess</span></span><br /><span data-ttu-id="8b8f6-177">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-177">-   eFastExitProcess</span></span><br /><span data-ttu-id="8b8f6-178">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="8b8f6-178">-   eRudeExitProcess</span></span><br /><span data-ttu-id="8b8f6-179">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="8b8f6-179">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b8f6-180">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8b8f6-180">Requirements</span></span>  

 <span data-ttu-id="8b8f6-181">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b8f6-181">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b8f6-182">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8b8f6-182">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b8f6-183">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8b8f6-183">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b8f6-184">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b8f6-184">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8f6-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b8f6-185">See also</span></span>

- [<span data-ttu-id="8b8f6-186">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8b8f6-186">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="8b8f6-187">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8b8f6-187">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="8b8f6-188">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b8f6-188">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
