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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9c2ebb2bc9c1137a4e3716d98387278959f77d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757319"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="1c4da-102">ICLRPolicyManager::SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="1c4da-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="1c4da-103">Legt einen Timeoutwert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="1c4da-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c4da-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c4da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c4da-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="1c4da-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der angibt, die common Language Runtime (CLR)-Vorgang für die einen Timeout festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1c4da-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="1c4da-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1c4da-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="1c4da-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="1c4da-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="1c4da-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="1c4da-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="1c4da-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="1c4da-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="1c4da-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="1c4da-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="1c4da-112">[in] Der neue Timeoutwert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="1c4da-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="1c4da-113">Der Wert INFINITE bewirkt, dass den Vorgang nicht zu einem Timeout.</span><span class="sxs-lookup"><span data-stu-id="1c4da-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c4da-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1c4da-114">Return Value</span></span>  
  
|<span data-ttu-id="1c4da-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c4da-115">HRESULT</span></span>|<span data-ttu-id="1c4da-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c4da-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c4da-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c4da-117">S_OK</span></span>|<span data-ttu-id="1c4da-118">`SetTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1c4da-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="1c4da-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1c4da-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1c4da-120">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1c4da-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1c4da-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1c4da-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1c4da-122">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1c4da-122">The call timed out.</span></span>|  
|<span data-ttu-id="1c4da-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1c4da-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1c4da-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1c4da-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1c4da-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1c4da-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1c4da-126">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1c4da-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1c4da-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c4da-127">E_FAIL</span></span>|<span data-ttu-id="1c4da-128">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1c4da-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1c4da-129">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c4da-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1c4da-130">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1c4da-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1c4da-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1c4da-131">E_INVALIDARG</span></span>|<span data-ttu-id="1c4da-132">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="1c4da-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c4da-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c4da-133">Requirements</span></span>  
 <span data-ttu-id="1c4da-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c4da-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c4da-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c4da-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c4da-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1c4da-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c4da-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c4da-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4da-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c4da-138">See also</span></span>

- [<span data-ttu-id="1c4da-139">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1c4da-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="1c4da-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c4da-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1c4da-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c4da-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
