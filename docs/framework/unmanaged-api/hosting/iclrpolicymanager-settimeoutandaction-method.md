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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c375fdffacccb27c20878c4e6adef9dd947148e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435523"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="435c0-102">ICLRPolicyManager::SetTimeoutAndAction-Methode</span><span class="sxs-lookup"><span data-stu-id="435c0-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="435c0-103">Legt einen Timeoutwert für den angegebenen Vorgang und gibt an, die Gruppenrichtlinien-Aktion, die die common Language Runtime (CLR) ausgeführt werden soll, wenn der Vorgang auftritt.</span><span class="sxs-lookup"><span data-stu-id="435c0-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="435c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="435c0-104">Syntax</span></span>  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="435c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="435c0-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="435c0-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der den Vorgang für die das Timeout und eine Richtlinie festgelegt `action`.</span><span class="sxs-lookup"><span data-stu-id="435c0-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="435c0-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="435c0-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="435c0-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="435c0-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="435c0-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="435c0-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="435c0-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="435c0-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="435c0-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="435c0-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="435c0-112">[in] Der neue Timeoutwert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="435c0-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="435c0-113">Der Wert INFINITE bewirkt, dass `operation` niemals zu einem Timeout führen.</span><span class="sxs-lookup"><span data-stu-id="435c0-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="435c0-114">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, der angibt, dass die CLR, wenn ausführen soll die Richtlinienaktion `operation` auftritt.</span><span class="sxs-lookup"><span data-stu-id="435c0-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="435c0-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="435c0-115">Return Value</span></span>  
  
|<span data-ttu-id="435c0-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="435c0-116">HRESULT</span></span>|<span data-ttu-id="435c0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="435c0-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="435c0-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="435c0-118">S_OK</span></span>|<span data-ttu-id="435c0-119">`SetTimeoutAndAction` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="435c0-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="435c0-120">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="435c0-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="435c0-121">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="435c0-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="435c0-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="435c0-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="435c0-123">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="435c0-123">The call timed out.</span></span>|  
|<span data-ttu-id="435c0-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="435c0-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="435c0-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="435c0-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="435c0-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="435c0-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="435c0-127">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="435c0-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="435c0-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="435c0-128">E_FAIL</span></span>|<span data-ttu-id="435c0-129">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="435c0-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="435c0-130">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="435c0-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="435c0-131">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="435c0-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="435c0-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="435c0-132">E_INVALIDARG</span></span>|<span data-ttu-id="435c0-133">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `action`.</span><span class="sxs-lookup"><span data-stu-id="435c0-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="435c0-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="435c0-134">Remarks</span></span>  
 <span data-ttu-id="435c0-135">`SetTimeoutAndAction` Kapselt die Funktionen des die [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) und [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) Methoden, und kann anstelle von sequenziellen Aufrufen dieser beiden Methoden aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="435c0-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="435c0-136">Nicht alle Werte für Aktivierungsrichtlinien Aktion können als das Timeoutverhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="435c0-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="435c0-137">Finden Sie im Abschnitt "Hinweise" in den Themen dieser beiden Methoden für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="435c0-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="435c0-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="435c0-138">Requirements</span></span>  
 <span data-ttu-id="435c0-139">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="435c0-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="435c0-140">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="435c0-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="435c0-141">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="435c0-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="435c0-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="435c0-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435c0-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="435c0-143">See Also</span></span>  
 [<span data-ttu-id="435c0-144">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="435c0-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="435c0-145">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="435c0-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="435c0-146">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="435c0-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="435c0-147">SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="435c0-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)  
 [<span data-ttu-id="435c0-148">ICLRPolicyManager:: SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="435c0-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
