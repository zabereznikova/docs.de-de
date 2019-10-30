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
ms.openlocfilehash: 2a6dc878f156d5d18970fed72c9722bab60f9ba8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120405"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="00214-102">ICLRRuntimeHost::UnloadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="00214-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="00214-103">Entlädt das verwaltete <xref:System.AppDomain>, das dem angegebenen numerischen Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="00214-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00214-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00214-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00214-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00214-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="00214-106">in Der numerische Bezeichner der zu entladenden Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="00214-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="00214-107">[in] `true`, um anzugeben, dass die Common Language Runtime (CLR) warten muss, bis die Ausführung des aktuellen Threads der Anwendung abgeschlossen ist, bevor versucht wird, die Anwendungsdomäne zu entladen.</span><span class="sxs-lookup"><span data-stu-id="00214-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00214-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="00214-108">Return Value</span></span>  
  
|<span data-ttu-id="00214-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00214-109">HRESULT</span></span>|<span data-ttu-id="00214-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00214-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00214-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="00214-111">S_OK</span></span>|<span data-ttu-id="00214-112">`UnloadAppDomain` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="00214-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="00214-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00214-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00214-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="00214-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00214-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00214-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00214-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="00214-116">The call timed out.</span></span>|  
|<span data-ttu-id="00214-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00214-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00214-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="00214-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00214-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00214-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00214-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="00214-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00214-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00214-121">E_FAIL</span></span>|<span data-ttu-id="00214-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="00214-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00214-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00214-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00214-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="00214-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00214-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00214-125">Remarks</span></span>  
 <span data-ttu-id="00214-126">Sie können den numerischen Bezeichner der Anwendungsdomäne abrufen, in der der aktuelle Thread ausgeführt wird, indem Sie [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)aufrufen.</span><span class="sxs-lookup"><span data-stu-id="00214-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="00214-127">Dieser Bezeichner entspricht der <xref:System.AppDomain.Id%2A>-Eigenschaft des verwalteten <xref:System.AppDomain> Typs.</span><span class="sxs-lookup"><span data-stu-id="00214-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00214-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00214-128">Requirements</span></span>  
 <span data-ttu-id="00214-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00214-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00214-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="00214-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00214-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="00214-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00214-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00214-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00214-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00214-133">See also</span></span>

- [<span data-ttu-id="00214-134">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00214-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
