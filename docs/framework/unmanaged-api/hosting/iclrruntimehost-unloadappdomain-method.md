---
title: ICLRRuntimeHost::UnloadAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad87599de1b6c3227f4b413ea84558ad690d250f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494388"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="926ba-102">ICLRRuntimeHost::UnloadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="926ba-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="926ba-103">Entlädt die verwaltete <xref:System.AppDomain> , die dem angegebenen numerischen Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="926ba-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="926ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="926ba-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="926ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="926ba-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="926ba-106">[in] Der numerische Bezeichner der Anwendungsdomäne zu nicht entladen.</span><span class="sxs-lookup"><span data-stu-id="926ba-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="926ba-107">[in] `true` , um anzugeben, dass die common Language Runtime (CLR) warten muss, bis sie die Ausführung von aktuellen Thread der Anwendung vor dem Entladen der Anwendungsdomäne beendet hat.</span><span class="sxs-lookup"><span data-stu-id="926ba-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="926ba-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="926ba-108">Return Value</span></span>  
  
|<span data-ttu-id="926ba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="926ba-109">HRESULT</span></span>|<span data-ttu-id="926ba-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="926ba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="926ba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="926ba-111">S_OK</span></span>|<span data-ttu-id="926ba-112">`UnloadAppDomain` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="926ba-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="926ba-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="926ba-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="926ba-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="926ba-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="926ba-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="926ba-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="926ba-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="926ba-116">The call timed out.</span></span>|  
|<span data-ttu-id="926ba-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="926ba-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="926ba-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="926ba-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="926ba-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="926ba-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="926ba-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="926ba-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="926ba-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="926ba-121">E_FAIL</span></span>|<span data-ttu-id="926ba-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="926ba-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="926ba-123">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="926ba-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="926ba-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="926ba-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="926ba-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="926ba-125">Remarks</span></span>  
 <span data-ttu-id="926ba-126">Sie können den numerischen Bezeichner der Anwendungsdomäne, in dem der aktuelle Thread, durch den Aufruf ausgeführt wird, abrufen [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="926ba-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="926ba-127">Dieser Bezeichner entspricht der <xref:System.AppDomain.Id%2A> Eigenschaft der verwalteten <xref:System.AppDomain> Typ.</span><span class="sxs-lookup"><span data-stu-id="926ba-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="926ba-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="926ba-128">Requirements</span></span>  
 <span data-ttu-id="926ba-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="926ba-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="926ba-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="926ba-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="926ba-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="926ba-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="926ba-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="926ba-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="926ba-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="926ba-133">See also</span></span>
- [<span data-ttu-id="926ba-134">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="926ba-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
