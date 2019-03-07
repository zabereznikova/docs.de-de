---
title: IHostSecurityContext::Capture-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityContext.Capture
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92b593248a7a196247a5b4c71a90cd8944665bbe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485277"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="fb32f-102">IHostSecurityContext::Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="fb32f-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="fb32f-103">Ruft einen Klon der [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) Instanz zurückgegeben, von einem Aufruf von [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="fb32f-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb32f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb32f-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb32f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb32f-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="fb32f-106">[out] Ein Zeiger auf die Adresse der einen Klon der `IHostSecurityContext` Objekt erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb32f-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb32f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fb32f-107">Return Value</span></span>  
  
|<span data-ttu-id="fb32f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb32f-108">HRESULT</span></span>|<span data-ttu-id="fb32f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb32f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb32f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb32f-110">S_OK</span></span>|<span data-ttu-id="fb32f-111">`Capture` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb32f-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="fb32f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fb32f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fb32f-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fb32f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fb32f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fb32f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fb32f-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fb32f-115">The call timed out.</span></span>|  
|<span data-ttu-id="fb32f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fb32f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fb32f-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fb32f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fb32f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fb32f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fb32f-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="fb32f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fb32f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb32f-120">E_FAIL</span></span>|<span data-ttu-id="fb32f-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fb32f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fb32f-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb32f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fb32f-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fb32f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb32f-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb32f-124">Remarks</span></span>  
 <span data-ttu-id="fb32f-125">Der Schnittstellenzeiger zurückgegeben, die von `Capture` ist ein Klon des erfassten Kontext.</span><span class="sxs-lookup"><span data-stu-id="fb32f-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="fb32f-126">Wenn diese Informationen über einen Punkt von asynchronem Code verschoben wird, wird seine Lebensdauer von der der Zeiger getrennt für die der Aufruf erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="fb32f-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="fb32f-127">Der ursprüngliche Zeiger kann aus diesem Grund aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="fb32f-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb32f-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb32f-128">Requirements</span></span>  
 <span data-ttu-id="fb32f-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb32f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb32f-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb32f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb32f-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fb32f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb32f-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb32f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb32f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb32f-133">See also</span></span>
- [<span data-ttu-id="fb32f-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb32f-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="fb32f-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb32f-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
