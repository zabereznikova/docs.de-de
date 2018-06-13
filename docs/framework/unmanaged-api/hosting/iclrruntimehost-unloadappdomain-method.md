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
ms.openlocfilehash: c7dba595953a305c9da33e255676c4b2dcae7a96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435581"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="8cd4d-102">ICLRRuntimeHost::UnloadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="8cd4d-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="8cd4d-103">Entlädt die verwaltete <xref:System.AppDomain> , die den angegebenen numerischen Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cd4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cd4d-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cd4d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8cd4d-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="8cd4d-106">[in] Den numerischen Bezeichner der Anwendungsdomäne zu entladen.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="8cd4d-107">[in] `true` um anzugeben, dass die common Language Runtime (CLR) warten muss, bis sie die aktuellen Thread der Anwendung ausführen, bevor Sie versuchen, die die Anwendungsdomäne entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cd4d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8cd4d-108">Return Value</span></span>  
  
|<span data-ttu-id="8cd4d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8cd4d-109">HRESULT</span></span>|<span data-ttu-id="8cd4d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cd4d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8cd4d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cd4d-111">S_OK</span></span>|<span data-ttu-id="8cd4d-112">`UnloadAppDomain` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="8cd4d-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="8cd4d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8cd4d-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8cd4d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8cd4d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8cd4d-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-116">The call timed out.</span></span>|  
|<span data-ttu-id="8cd4d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8cd4d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8cd4d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8cd4d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8cd4d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8cd4d-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8cd4d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8cd4d-121">E_FAIL</span></span>|<span data-ttu-id="8cd4d-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8cd4d-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8cd4d-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cd4d-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8cd4d-125">Remarks</span></span>  
 <span data-ttu-id="8cd4d-126">Sie können den numerischen Bezeichner der Anwendungsdomäne, in dem der aktuelle Thread, durch den Aufruf ausgeführt wird, abrufen [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="8cd4d-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="8cd4d-127">Dieser Bezeichner entspricht der <xref:System.AppDomain.Id%2A> Eigenschaft der verwalteten <xref:System.AppDomain> Typ.</span><span class="sxs-lookup"><span data-stu-id="8cd4d-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cd4d-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8cd4d-128">Requirements</span></span>  
 <span data-ttu-id="8cd4d-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cd4d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cd4d-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8cd4d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cd4d-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8cd4d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cd4d-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cd4d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd4d-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cd4d-133">See Also</span></span>  
 [<span data-ttu-id="8cd4d-134">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8cd4d-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
