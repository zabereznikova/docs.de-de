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
ms.openlocfilehash: b16cc6a899b1ad5c814c29a93c6125250ca8186d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133574"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="df1c5-102">ICLRPolicyManager::SetTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="df1c5-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="df1c5-103">Legt einen Timeoutwert für den angegebenen Vorgang fest.</span><span class="sxs-lookup"><span data-stu-id="df1c5-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df1c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df1c5-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df1c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df1c5-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="df1c5-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der angibt, die common Language Runtime (CLR)-Vorgang für die einen Timeout festgelegt.</span><span class="sxs-lookup"><span data-stu-id="df1c5-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="df1c5-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="df1c5-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="df1c5-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="df1c5-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="df1c5-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="df1c5-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="df1c5-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="df1c5-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="df1c5-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="df1c5-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="df1c5-112">[in] Der neue Timeoutwert in Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="df1c5-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="df1c5-113">Der Wert INFINITE bewirkt, dass den Vorgang nicht zu einem Timeout.</span><span class="sxs-lookup"><span data-stu-id="df1c5-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df1c5-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="df1c5-114">Return Value</span></span>  
  
|<span data-ttu-id="df1c5-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df1c5-115">HRESULT</span></span>|<span data-ttu-id="df1c5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df1c5-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df1c5-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="df1c5-117">S_OK</span></span>|`SetTimeout` <span data-ttu-id="df1c5-118">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="df1c5-118">returned successfully.</span></span>|  
|<span data-ttu-id="df1c5-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df1c5-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df1c5-120">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="df1c5-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df1c5-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df1c5-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df1c5-122">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="df1c5-122">The call timed out.</span></span>|  
|<span data-ttu-id="df1c5-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df1c5-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df1c5-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="df1c5-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df1c5-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df1c5-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df1c5-126">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="df1c5-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df1c5-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df1c5-127">E_FAIL</span></span>|<span data-ttu-id="df1c5-128">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="df1c5-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df1c5-129">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df1c5-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df1c5-130">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="df1c5-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="df1c5-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="df1c5-131">E_INVALIDARG</span></span>|<span data-ttu-id="df1c5-132">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="df1c5-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df1c5-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df1c5-133">Requirements</span></span>  
 <span data-ttu-id="df1c5-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df1c5-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df1c5-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df1c5-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df1c5-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="df1c5-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="df1c5-137">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="df1c5-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df1c5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df1c5-138">See also</span></span>

- [<span data-ttu-id="df1c5-139">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="df1c5-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="df1c5-140">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df1c5-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="df1c5-141">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df1c5-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
