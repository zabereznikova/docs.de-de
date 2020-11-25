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
ms.openlocfilehash: cc5d0d65d213d952c0897a72d8ec38ea6b8b22db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700664"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="311ca-102">ICLRRuntimeHost::UnloadAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="311ca-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>

<span data-ttu-id="311ca-103">Entlädt das verwaltete <xref:System.AppDomain> , das dem angegebenen numerischen Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="311ca-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="311ca-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="311ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="311ca-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="311ca-106">in Der numerische Bezeichner der zu entladenden Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="311ca-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="311ca-107">[in] `true` , um anzugeben, dass die Common Language Runtime (CLR) warten muss, bis die Ausführung des aktuellen Threads der Anwendung abgeschlossen ist, bevor versucht wird, die Anwendungsdomäne zu entladen.</span><span class="sxs-lookup"><span data-stu-id="311ca-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="311ca-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="311ca-108">Return Value</span></span>  
  
|<span data-ttu-id="311ca-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="311ca-109">HRESULT</span></span>|<span data-ttu-id="311ca-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="311ca-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="311ca-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="311ca-111">S_OK</span></span>|<span data-ttu-id="311ca-112">`UnloadAppDomain` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="311ca-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="311ca-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="311ca-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="311ca-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="311ca-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="311ca-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="311ca-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="311ca-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="311ca-116">The call timed out.</span></span>|  
|<span data-ttu-id="311ca-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="311ca-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="311ca-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="311ca-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="311ca-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="311ca-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="311ca-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="311ca-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="311ca-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="311ca-121">E_FAIL</span></span>|<span data-ttu-id="311ca-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="311ca-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="311ca-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="311ca-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="311ca-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="311ca-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="311ca-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="311ca-125">Remarks</span></span>  

 <span data-ttu-id="311ca-126">Sie können den numerischen Bezeichner der Anwendungsdomäne abrufen, in der der aktuelle Thread ausgeführt wird, indem Sie [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md)aufrufen.</span><span class="sxs-lookup"><span data-stu-id="311ca-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="311ca-127">Dieser Bezeichner entspricht der- <xref:System.AppDomain.Id%2A> Eigenschaft des verwalteten <xref:System.AppDomain> Typs.</span><span class="sxs-lookup"><span data-stu-id="311ca-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="311ca-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="311ca-128">Requirements</span></span>  

 <span data-ttu-id="311ca-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="311ca-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="311ca-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="311ca-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="311ca-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="311ca-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="311ca-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="311ca-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="311ca-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="311ca-133">See also</span></span>

- [<span data-ttu-id="311ca-134">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="311ca-134">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
