---
title: IHostSecurityContext::Capture-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext.Capture
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 100ce151b81fb240434b1072be8fe8c354f85440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="c432e-102">IHostSecurityContext::Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="c432e-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="c432e-103">Ruft einen Klon der [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) Instanz zurückgegeben, Aufrufen von [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="c432e-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c432e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c432e-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c432e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c432e-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="c432e-106">[out] Ein Zeiger auf die Adresse des einen Klon der `IHostSecurityContext` Objekt aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c432e-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c432e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c432e-107">Return Value</span></span>  
  
|<span data-ttu-id="c432e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c432e-108">HRESULT</span></span>|<span data-ttu-id="c432e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c432e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c432e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c432e-110">S_OK</span></span>|<span data-ttu-id="c432e-111">`Capture`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c432e-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="c432e-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="c432e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c432e-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c432e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c432e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c432e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c432e-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c432e-115">The call timed out.</span></span>|  
|<span data-ttu-id="c432e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c432e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c432e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c432e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c432e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c432e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c432e-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c432e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c432e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c432e-120">E_FAIL</span></span>|<span data-ttu-id="c432e-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c432e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c432e-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="c432e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c432e-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c432e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c432e-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c432e-124">Remarks</span></span>  
 <span data-ttu-id="c432e-125">Der Schnittstellenzeiger, der vom zurückgegebenen `Capture` ist ein Klon des erfassten Kontext.</span><span class="sxs-lookup"><span data-stu-id="c432e-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="c432e-126">Wenn diese Informationen über einen asynchronen Codepunkt verschoben wird, ist seine Lebensdauer von, des Zeigers getrennt, für den der Aufruf erfolgte.</span><span class="sxs-lookup"><span data-stu-id="c432e-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="c432e-127">Der ursprüngliche Zeiger kann daher freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c432e-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c432e-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c432e-128">Requirements</span></span>  
 <span data-ttu-id="c432e-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c432e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c432e-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c432e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c432e-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c432e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c432e-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c432e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c432e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c432e-133">See Also</span></span>  
 [<span data-ttu-id="c432e-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c432e-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="c432e-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c432e-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
