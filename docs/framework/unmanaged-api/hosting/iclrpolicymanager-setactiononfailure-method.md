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
ms.openlocfilehash: 727cd82226b9a59c4879ffea5e87f93dd5fe38c9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504107"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="bc0d6-102">ICLRPolicyManager::SetActionOnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="bc0d6-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="bc0d6-103">Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc0d6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc0d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc0d6-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="bc0d6-106">in Einer der [EClrFailure](eclrfailure-enumeration.md) -Werte, der den Typ des Fehlers angibt, für den eine Aktion ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="bc0d6-107">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die durchgeführt werden soll, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="bc0d6-108">Eine Liste der unterstützten Werte finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="bc0d6-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc0d6-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bc0d6-109">Return Value</span></span>  
  
|<span data-ttu-id="bc0d6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc0d6-110">HRESULT</span></span>|<span data-ttu-id="bc0d6-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc0d6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc0d6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc0d6-112">S_OK</span></span>|<span data-ttu-id="bc0d6-113">`SetActionOnFailure`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="bc0d6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bc0d6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bc0d6-115">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bc0d6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bc0d6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bc0d6-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-117">The call timed out.</span></span>|  
|<span data-ttu-id="bc0d6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bc0d6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bc0d6-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bc0d6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bc0d6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bc0d6-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bc0d6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc0d6-122">E_FAIL</span></span>|<span data-ttu-id="bc0d6-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bc0d6-124">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bc0d6-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bc0d6-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bc0d6-126">E_INVALIDARG</span></span>|<span data-ttu-id="bc0d6-127">Eine Richtlinien Aktion kann für den angegebenen Vorgang nicht festgelegt werden, oder für den Vorgang wurde eine ungültige Richtlinien Aktion angegeben.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc0d6-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bc0d6-128">Remarks</span></span>  
 <span data-ttu-id="bc0d6-129">Standardmäßig löst die CLR eine Ausnahme aus, wenn Sie eine Ressource, z. b. Arbeitsspeicher, nicht zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="bc0d6-130">`SetActionOnFailure`ermöglicht dem Host, dieses Verhalten durch Angeben der Richtlinien Aktion, die bei einem Fehler ausgeführt werden soll, zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="bc0d6-131">In der folgenden Tabelle werden die Kombinationen der unterstützten [EClrFailure](eclrfailure-enumeration.md) -und [EPolicyAction](epolicyaction-enumeration.md) -Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc0d6-131">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="bc0d6-132">(Das FAIL_ Präfix wird in [EClrFailure](eclrfailure-enumeration.md) -Werten weggelassen.)</span><span class="sxs-lookup"><span data-stu-id="bc0d6-132">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="bc0d6-133">Nicht criticalresource</span><span class="sxs-lookup"><span data-stu-id="bc0d6-133">NonCriticalResource</span></span>|<span data-ttu-id="bc0d6-134">Criticalresource</span><span class="sxs-lookup"><span data-stu-id="bc0d6-134">CriticalResource</span></span>|<span data-ttu-id="bc0d6-135">Fatalruntime</span><span class="sxs-lookup"><span data-stu-id="bc0d6-135">FatalRuntime</span></span>|<span data-ttu-id="bc0d6-136">Waisen-edlock</span><span class="sxs-lookup"><span data-stu-id="bc0d6-136">OrphanedLock</span></span>|<span data-ttu-id="bc0d6-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="bc0d6-137">StackOverflow</span></span>|<span data-ttu-id="bc0d6-138">Zugriffsverletzung</span><span class="sxs-lookup"><span data-stu-id="bc0d6-138">AccessViolation</span></span>|<span data-ttu-id="bc0d6-139">Code Contract</span><span class="sxs-lookup"><span data-stu-id="bc0d6-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="bc0d6-140">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-140">X</span></span>|<span data-ttu-id="bc0d6-141">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-141">X</span></span>||||<span data-ttu-id="bc0d6-142">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-142">N/A</span></span>||  
|<span data-ttu-id="bc0d6-143">ethrowexception</span><span class="sxs-lookup"><span data-stu-id="bc0d6-143">eThrowException</span></span>|<span data-ttu-id="bc0d6-144">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-144">X</span></span>|<span data-ttu-id="bc0d6-145">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-145">X</span></span>||||<span data-ttu-id="bc0d6-146">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="bc0d6-147">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-147">X</span></span>|<span data-ttu-id="bc0d6-148">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-148">X</span></span>||||<span data-ttu-id="bc0d6-149">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-149">N/A</span></span>|<span data-ttu-id="bc0d6-150">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="bc0d6-151">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-151">X</span></span>|<span data-ttu-id="bc0d6-152">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-152">X</span></span>||||<span data-ttu-id="bc0d6-153">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-153">N/A</span></span>|<span data-ttu-id="bc0d6-154">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="bc0d6-155">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-155">X</span></span>|<span data-ttu-id="bc0d6-156">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-156">X</span></span>||<span data-ttu-id="bc0d6-157">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-157">X</span></span>||<span data-ttu-id="bc0d6-158">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-158">N/A</span></span>|<span data-ttu-id="bc0d6-159">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="bc0d6-160">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-160">X</span></span>|<span data-ttu-id="bc0d6-161">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-161">X</span></span>||<span data-ttu-id="bc0d6-162">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-162">X</span></span>|<span data-ttu-id="bc0d6-163">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-163">X</span></span>|<span data-ttu-id="bc0d6-164">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-164">N/A</span></span>|<span data-ttu-id="bc0d6-165">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="bc0d6-166">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-166">X</span></span>|<span data-ttu-id="bc0d6-167">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-167">X</span></span>||<span data-ttu-id="bc0d6-168">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-168">X</span></span>|<span data-ttu-id="bc0d6-169">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-169">X</span></span>|<span data-ttu-id="bc0d6-170">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-170">N/A</span></span>|<span data-ttu-id="bc0d6-171">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-171">X</span></span>|  
|<span data-ttu-id="bc0d6-172">efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="bc0d6-172">eFastExitProcess</span></span>|<span data-ttu-id="bc0d6-173">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-173">X</span></span>|<span data-ttu-id="bc0d6-174">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-174">X</span></span>||<span data-ttu-id="bc0d6-175">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-175">X</span></span>|<span data-ttu-id="bc0d6-176">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-176">X</span></span>|<span data-ttu-id="bc0d6-177">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="bc0d6-178">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-178">X</span></span>|<span data-ttu-id="bc0d6-179">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-179">X</span></span>|<span data-ttu-id="bc0d6-180">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-180">X</span></span>|<span data-ttu-id="bc0d6-181">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-181">X</span></span>|<span data-ttu-id="bc0d6-182">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-182">X</span></span>|<span data-ttu-id="bc0d6-183">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="bc0d6-184">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-184">X</span></span>|<span data-ttu-id="bc0d6-185">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-185">X</span></span>|<span data-ttu-id="bc0d6-186">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-186">X</span></span>|<span data-ttu-id="bc0d6-187">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-187">X</span></span>|<span data-ttu-id="bc0d6-188">X</span><span class="sxs-lookup"><span data-stu-id="bc0d6-188">X</span></span>|<span data-ttu-id="bc0d6-189">–</span><span class="sxs-lookup"><span data-stu-id="bc0d6-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="bc0d6-190">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bc0d6-190">Requirements</span></span>  
 <span data-ttu-id="bc0d6-191">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc0d6-191">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc0d6-192">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="bc0d6-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc0d6-193">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bc0d6-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc0d6-194">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc0d6-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc0d6-195">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bc0d6-195">See also</span></span>

- [<span data-ttu-id="bc0d6-196">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bc0d6-196">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="bc0d6-197">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bc0d6-197">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="bc0d6-198">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc0d6-198">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="bc0d6-199">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc0d6-199">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
