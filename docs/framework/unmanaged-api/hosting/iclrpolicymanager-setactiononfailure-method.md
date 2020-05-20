---
title: ICLRPolicyManager::SetActionOnFailure-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: fb2ecc80f272a3fc9b63b20c5956e7a28f117784
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703460"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="e7b5f-102">ICLRPolicyManager::SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="e7b5f-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="e7b5f-103">Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7b5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7b5f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7b5f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7b5f-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="e7b5f-106">in Einer der [EClrFailure](eclrfailure-enumeration.md) -Werte, der den Typ des Fehlers angibt, für den eine Aktion ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="e7b5f-107">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die durchgeführt werden soll, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="e7b5f-108">Eine Liste der unterstützten Werte finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="e7b5f-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7b5f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e7b5f-109">Return Value</span></span>  
  
|<span data-ttu-id="e7b5f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7b5f-110">HRESULT</span></span>|<span data-ttu-id="e7b5f-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e7b5f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7b5f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7b5f-112">S_OK</span></span>|<span data-ttu-id="e7b5f-113">`SetActionOnFailure`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="e7b5f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7b5f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7b5f-115">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e7b5f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7b5f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7b5f-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-117">The call timed out.</span></span>|  
|<span data-ttu-id="e7b5f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7b5f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7b5f-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7b5f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7b5f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7b5f-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7b5f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7b5f-122">E_FAIL</span></span>|<span data-ttu-id="e7b5f-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7b5f-124">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7b5f-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e7b5f-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e7b5f-126">E_INVALIDARG</span></span>|<span data-ttu-id="e7b5f-127">Eine Richtlinien Aktion kann für den angegebenen Vorgang nicht festgelegt werden, oder für den Vorgang wurde eine ungültige Richtlinien Aktion angegeben.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7b5f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7b5f-128">Remarks</span></span>  
 <span data-ttu-id="e7b5f-129">Standardmäßig löst die CLR eine Ausnahme aus, wenn Sie eine Ressource, z. b. Arbeitsspeicher, nicht zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="e7b5f-130">`SetActionOnFailure`ermöglicht dem Host, dieses Verhalten durch Angeben der Richtlinien Aktion, die bei einem Fehler ausgeführt werden soll, zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="e7b5f-131">In der folgenden Tabelle werden die Kombinationen der unterstützten [EClrFailure](eclrfailure-enumeration.md) -und [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) -Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7b5f-131">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="e7b5f-132">(Das FAIL_ Präfix wird in [EClrFailure](eclrfailure-enumeration.md) -Werten weggelassen.)</span><span class="sxs-lookup"><span data-stu-id="e7b5f-132">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="e7b5f-133">Nicht criticalresource</span><span class="sxs-lookup"><span data-stu-id="e7b5f-133">NonCriticalResource</span></span>|<span data-ttu-id="e7b5f-134">Criticalresource</span><span class="sxs-lookup"><span data-stu-id="e7b5f-134">CriticalResource</span></span>|<span data-ttu-id="e7b5f-135">Fatalruntime</span><span class="sxs-lookup"><span data-stu-id="e7b5f-135">FatalRuntime</span></span>|<span data-ttu-id="e7b5f-136">Waisen-edlock</span><span class="sxs-lookup"><span data-stu-id="e7b5f-136">OrphanedLock</span></span>|<span data-ttu-id="e7b5f-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="e7b5f-137">StackOverflow</span></span>|<span data-ttu-id="e7b5f-138">Zugriffsverletzung</span><span class="sxs-lookup"><span data-stu-id="e7b5f-138">AccessViolation</span></span>|<span data-ttu-id="e7b5f-139">Code Contract</span><span class="sxs-lookup"><span data-stu-id="e7b5f-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="e7b5f-140">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-140">X</span></span>|<span data-ttu-id="e7b5f-141">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-141">X</span></span>||||<span data-ttu-id="e7b5f-142">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-142">N/A</span></span>||  
|<span data-ttu-id="e7b5f-143">ethrowexception</span><span class="sxs-lookup"><span data-stu-id="e7b5f-143">eThrowException</span></span>|<span data-ttu-id="e7b5f-144">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-144">X</span></span>|<span data-ttu-id="e7b5f-145">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-145">X</span></span>||||<span data-ttu-id="e7b5f-146">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="e7b5f-147">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-147">X</span></span>|<span data-ttu-id="e7b5f-148">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-148">X</span></span>||||<span data-ttu-id="e7b5f-149">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-149">N/A</span></span>|<span data-ttu-id="e7b5f-150">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="e7b5f-151">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-151">X</span></span>|<span data-ttu-id="e7b5f-152">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-152">X</span></span>||||<span data-ttu-id="e7b5f-153">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-153">N/A</span></span>|<span data-ttu-id="e7b5f-154">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="e7b5f-155">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-155">X</span></span>|<span data-ttu-id="e7b5f-156">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-156">X</span></span>||<span data-ttu-id="e7b5f-157">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-157">X</span></span>||<span data-ttu-id="e7b5f-158">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-158">N/A</span></span>|<span data-ttu-id="e7b5f-159">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="e7b5f-160">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-160">X</span></span>|<span data-ttu-id="e7b5f-161">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-161">X</span></span>||<span data-ttu-id="e7b5f-162">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-162">X</span></span>|<span data-ttu-id="e7b5f-163">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-163">X</span></span>|<span data-ttu-id="e7b5f-164">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-164">N/A</span></span>|<span data-ttu-id="e7b5f-165">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="e7b5f-166">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-166">X</span></span>|<span data-ttu-id="e7b5f-167">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-167">X</span></span>||<span data-ttu-id="e7b5f-168">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-168">X</span></span>|<span data-ttu-id="e7b5f-169">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-169">X</span></span>|<span data-ttu-id="e7b5f-170">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-170">N/A</span></span>|<span data-ttu-id="e7b5f-171">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-171">X</span></span>|  
|<span data-ttu-id="e7b5f-172">efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="e7b5f-172">eFastExitProcess</span></span>|<span data-ttu-id="e7b5f-173">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-173">X</span></span>|<span data-ttu-id="e7b5f-174">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-174">X</span></span>||<span data-ttu-id="e7b5f-175">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-175">X</span></span>|<span data-ttu-id="e7b5f-176">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-176">X</span></span>|<span data-ttu-id="e7b5f-177">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="e7b5f-178">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-178">X</span></span>|<span data-ttu-id="e7b5f-179">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-179">X</span></span>|<span data-ttu-id="e7b5f-180">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-180">X</span></span>|<span data-ttu-id="e7b5f-181">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-181">X</span></span>|<span data-ttu-id="e7b5f-182">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-182">X</span></span>|<span data-ttu-id="e7b5f-183">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="e7b5f-184">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-184">X</span></span>|<span data-ttu-id="e7b5f-185">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-185">X</span></span>|<span data-ttu-id="e7b5f-186">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-186">X</span></span>|<span data-ttu-id="e7b5f-187">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-187">X</span></span>|<span data-ttu-id="e7b5f-188">X</span><span class="sxs-lookup"><span data-stu-id="e7b5f-188">X</span></span>|<span data-ttu-id="e7b5f-189">–</span><span class="sxs-lookup"><span data-stu-id="e7b5f-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="e7b5f-190">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7b5f-190">Requirements</span></span>  
 <span data-ttu-id="e7b5f-191">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7b5f-191">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7b5f-192">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e7b5f-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7b5f-193">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e7b5f-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7b5f-194">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7b5f-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b5f-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7b5f-195">See also</span></span>

- [<span data-ttu-id="e7b5f-196">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e7b5f-196">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="e7b5f-197">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e7b5f-197">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="e7b5f-198">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7b5f-198">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e7b5f-199">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7b5f-199">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
