---
title: ICLRPolicyManager::SetTimeout-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
ms.openlocfilehash: b3e66a1e04ca3f3031adf1f0f7f71d689ee76b04
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703418"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="db749-102">ICLRPolicyManager::SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="db749-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="db749-103">Legt einen Timeout Wert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="db749-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db749-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db749-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db749-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db749-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="db749-106">in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der den Common Language Runtime (CLR)-Vorgang angibt, für den ein Timeout festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="db749-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="db749-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="db749-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="db749-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="db749-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="db749-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="db749-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="db749-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="db749-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="db749-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="db749-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="db749-112">in Der neue Timeout Wert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="db749-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="db749-113">Der Wert unendlich bewirkt, dass für den Vorgang kein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="db749-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db749-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db749-114">Return Value</span></span>  
  
|<span data-ttu-id="db749-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db749-115">HRESULT</span></span>|<span data-ttu-id="db749-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="db749-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db749-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="db749-117">S_OK</span></span>|<span data-ttu-id="db749-118">`SetTimeout`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="db749-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="db749-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db749-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db749-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="db749-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db749-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db749-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db749-122">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="db749-122">The call timed out.</span></span>|  
|<span data-ttu-id="db749-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db749-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db749-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="db749-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db749-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db749-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db749-126">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="db749-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db749-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db749-127">E_FAIL</span></span>|<span data-ttu-id="db749-128">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="db749-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db749-129">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db749-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db749-130">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="db749-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="db749-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="db749-131">E_INVALIDARG</span></span>|<span data-ttu-id="db749-132">Für den angegebenen kann kein Timeout festgelegt werden `operation` , oder für wurde ein ungültiger Wert angegeben `operation` .</span><span class="sxs-lookup"><span data-stu-id="db749-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db749-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db749-133">Requirements</span></span>  
 <span data-ttu-id="db749-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db749-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db749-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="db749-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db749-136">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db749-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db749-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db749-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db749-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db749-138">See also</span></span>

- [<span data-ttu-id="db749-139">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="db749-139">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="db749-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db749-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="db749-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db749-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
