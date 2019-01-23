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
ms.openlocfilehash: 6194478922bb1634f8a96de420fb17af10666322
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560957"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="27934-102">ICLRRuntimeHost::UnloadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="27934-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="27934-103">Entlädt die verwaltete <xref:System.AppDomain> , die dem angegebenen numerischen Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="27934-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27934-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27934-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27934-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27934-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="27934-106">[in] Der numerische Bezeichner der Anwendungsdomäne zu nicht entladen.</span><span class="sxs-lookup"><span data-stu-id="27934-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="27934-107">[in] `true` , um anzugeben, dass die common Language Runtime (CLR) warten muss, bis sie die Ausführung von aktuellen Thread der Anwendung vor dem Entladen der Anwendungsdomäne beendet hat.</span><span class="sxs-lookup"><span data-stu-id="27934-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27934-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="27934-108">Return Value</span></span>  
  
|<span data-ttu-id="27934-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27934-109">HRESULT</span></span>|<span data-ttu-id="27934-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27934-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27934-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="27934-111">S_OK</span></span>|<span data-ttu-id="27934-112">`UnloadAppDomain` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27934-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="27934-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27934-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27934-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="27934-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27934-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27934-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27934-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="27934-116">The call timed out.</span></span>|  
|<span data-ttu-id="27934-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27934-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27934-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="27934-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27934-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27934-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27934-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="27934-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27934-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27934-121">E_FAIL</span></span>|<span data-ttu-id="27934-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="27934-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27934-123">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27934-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27934-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="27934-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27934-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27934-125">Remarks</span></span>  
 <span data-ttu-id="27934-126">Sie können den numerischen Bezeichner der Anwendungsdomäne, in dem der aktuelle Thread, durch den Aufruf ausgeführt wird, abrufen [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="27934-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="27934-127">Dieser Bezeichner entspricht der <xref:System.AppDomain.Id%2A> Eigenschaft der verwalteten <xref:System.AppDomain> Typ.</span><span class="sxs-lookup"><span data-stu-id="27934-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27934-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27934-128">Requirements</span></span>  
 <span data-ttu-id="27934-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27934-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27934-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27934-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27934-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="27934-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27934-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27934-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27934-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27934-133">See also</span></span>
- [<span data-ttu-id="27934-134">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27934-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
