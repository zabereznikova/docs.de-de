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
ms.openlocfilehash: 3ddd78ea35d5709abb30af085b2212a09b28c2ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725559"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="7670a-102">ICLRPolicyManager::SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="7670a-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>

<span data-ttu-id="7670a-103">Gibt die Richtlinien Aktion an, die vom Common Language Runtime (CLR) ausgeführt werden soll, wenn für den angegebenen Vorgang ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="7670a-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7670a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7670a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7670a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7670a-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="7670a-106">in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der den Vorgang angibt, für den die Timeout Aktion angegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="7670a-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="7670a-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7670a-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="7670a-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="7670a-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="7670a-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="7670a-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="7670a-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="7670a-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="7670a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="7670a-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="7670a-112">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die bei einem Timeout des Vorgangs ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7670a-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7670a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7670a-113">Return Value</span></span>  
  
|<span data-ttu-id="7670a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7670a-114">HRESULT</span></span>|<span data-ttu-id="7670a-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7670a-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7670a-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7670a-116">S_OK</span></span>|<span data-ttu-id="7670a-117">`SetActionOnTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7670a-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="7670a-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7670a-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7670a-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7670a-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7670a-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7670a-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7670a-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7670a-121">The call timed out.</span></span>|  
|<span data-ttu-id="7670a-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7670a-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7670a-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7670a-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7670a-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7670a-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7670a-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7670a-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7670a-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7670a-126">E_FAIL</span></span>|<span data-ttu-id="7670a-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7670a-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7670a-128">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7670a-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7670a-129">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7670a-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7670a-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7670a-130">E_INVALIDARG</span></span>|<span data-ttu-id="7670a-131">Für den angegebenen kann kein Timeout festgelegt werden `operation` , oder für wurde ein ungültiger Wert angegeben `operation` .</span><span class="sxs-lookup"><span data-stu-id="7670a-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7670a-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7670a-132">Remarks</span></span>  

 <span data-ttu-id="7670a-133">Der Timeout Wert kann entweder das von der CLR festgelegte Standard Timeout oder ein Wert sein, der vom Host in einem Aufrufen der [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) -Methode angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7670a-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="7670a-134">Nicht alle Richtlinien Aktionswerte können als Timeout Verhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7670a-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="7670a-135">`SetActionOnTimeout` wird in der Regel nur zum eskalieren des Verhaltens verwendet.</span><span class="sxs-lookup"><span data-stu-id="7670a-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="7670a-136">Beispielsweise kann ein Host angeben, dass Thread Abbrüche in grobe Thread Abbrüche umgewandelt werden, aber nicht das Gegenteil angeben können.</span><span class="sxs-lookup"><span data-stu-id="7670a-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="7670a-137">In der folgenden Tabelle werden die gültigen Werte `action` für gültige `operation` Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7670a-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="7670a-138">Wert für `operation`</span><span class="sxs-lookup"><span data-stu-id="7670a-138">Value for `operation`</span></span>|<span data-ttu-id="7670a-139">Gültige Werte für `action`</span><span class="sxs-lookup"><span data-stu-id="7670a-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="7670a-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="7670a-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="7670a-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="7670a-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="7670a-142">-erudeabortthread</span><span class="sxs-lookup"><span data-stu-id="7670a-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="7670a-143">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="7670a-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="7670a-144">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="7670a-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="7670a-145">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="7670a-145">-   eExitProcess</span></span><br /><span data-ttu-id="7670a-146">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="7670a-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="7670a-147">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="7670a-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="7670a-148">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="7670a-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="7670a-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="7670a-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="7670a-150">-eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="7670a-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="7670a-151">-erudeunloadappdomain</span><span class="sxs-lookup"><span data-stu-id="7670a-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="7670a-152">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="7670a-152">-   eExitProcess</span></span><br /><span data-ttu-id="7670a-153">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="7670a-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="7670a-154">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="7670a-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="7670a-155">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="7670a-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="7670a-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="7670a-156">OPR_ProcessExit</span></span>|<span data-ttu-id="7670a-157">-eexitprocess</span><span class="sxs-lookup"><span data-stu-id="7670a-157">-   eExitProcess</span></span><br /><span data-ttu-id="7670a-158">-efastexitprocess</span><span class="sxs-lookup"><span data-stu-id="7670a-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="7670a-159">-eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="7670a-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="7670a-160">-edisableruntime</span><span class="sxs-lookup"><span data-stu-id="7670a-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7670a-161">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7670a-161">Requirements</span></span>  

 <span data-ttu-id="7670a-162">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7670a-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7670a-163">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7670a-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7670a-164">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7670a-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7670a-165">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7670a-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7670a-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7670a-166">See also</span></span>

- [<span data-ttu-id="7670a-167">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7670a-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="7670a-168">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7670a-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="7670a-169">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7670a-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="7670a-170">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7670a-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
