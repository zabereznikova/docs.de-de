---
title: ICLRPolicyManager::SetTimeoutAndAction-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: 02e836601be72d54f561e077cd3c466470bafb25
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504094"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="d3fac-102">ICLRPolicyManager::SetTimeoutAndAction-Methode</span><span class="sxs-lookup"><span data-stu-id="d3fac-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="d3fac-103">Legt einen Timeout Wert für den angegebenen Vorgang fest und gibt die Richtlinien Aktion an, die der Common Language Runtime (CLR) ausführen soll, wenn der Vorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d3fac-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3fac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3fac-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3fac-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d3fac-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="d3fac-106">in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der den Vorgang angibt, für den das Timeout und die Richtlinie festgelegt werden sollen `action` .</span><span class="sxs-lookup"><span data-stu-id="d3fac-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="d3fac-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d3fac-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="d3fac-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="d3fac-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="d3fac-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="d3fac-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="d3fac-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d3fac-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="d3fac-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="d3fac-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="d3fac-112">in Der neue Timeout Wert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="d3fac-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="d3fac-113">Der Wert unendlich bewirkt, dass nie ein Timeout auftritt `operation` .</span><span class="sxs-lookup"><span data-stu-id="d3fac-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="d3fac-114">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Richtlinien Aktion angibt, die die CLR bei Auftreten durchführen soll `operation` .</span><span class="sxs-lookup"><span data-stu-id="d3fac-114">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3fac-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d3fac-115">Return Value</span></span>  
  
|<span data-ttu-id="d3fac-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3fac-116">HRESULT</span></span>|<span data-ttu-id="d3fac-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d3fac-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3fac-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3fac-118">S_OK</span></span>|<span data-ttu-id="d3fac-119">`SetTimeoutAndAction`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d3fac-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="d3fac-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3fac-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3fac-121">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d3fac-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3fac-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3fac-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3fac-123">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d3fac-123">The call timed out.</span></span>|  
|<span data-ttu-id="d3fac-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3fac-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3fac-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d3fac-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3fac-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3fac-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3fac-127">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d3fac-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3fac-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3fac-128">E_FAIL</span></span>|<span data-ttu-id="d3fac-129">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d3fac-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3fac-130">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3fac-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3fac-131">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d3fac-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d3fac-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d3fac-132">E_INVALIDARG</span></span>|<span data-ttu-id="d3fac-133">Für den angegebenen kann kein Timeout festgelegt werden `operation` , oder für wurde ein ungültiger Wert angegeben `action` .</span><span class="sxs-lookup"><span data-stu-id="d3fac-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3fac-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d3fac-134">Remarks</span></span>  
 <span data-ttu-id="d3fac-135">`SetTimeoutAndAction`kapselt die Funktionen der [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) -Methode und der [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) -Methode und kann anstelle von sequenziellen Aufrufen dieser beiden Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d3fac-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d3fac-136">Nicht alle Richtlinien Aktionswerte können als Timeout Verhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d3fac-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="d3fac-137">Gültige Werte finden Sie in den Abschnitten zu den Themen zu diesen beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="d3fac-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3fac-138">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d3fac-138">Requirements</span></span>  
 <span data-ttu-id="d3fac-139">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3fac-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3fac-140">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d3fac-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3fac-141">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d3fac-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3fac-142">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3fac-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3fac-143">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="d3fac-143">See also</span></span>

- [<span data-ttu-id="d3fac-144">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d3fac-144">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="d3fac-145">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d3fac-145">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="d3fac-146">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3fac-146">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="d3fac-147">SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="d3fac-147">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="d3fac-148">ICLRPolicyManager:: SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="d3fac-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](iclrpolicymanager-settimeoutandaction-method.md)
