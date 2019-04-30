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
ms.openlocfilehash: e0f6ae812b64080a2c4d236a2be02ad81c4a11b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993017"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="0ca27-102">IHostSecurityContext::Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="0ca27-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="0ca27-103">Ruft einen Klon der [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) Instanz zurückgegeben, von einem Aufruf von [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="0ca27-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ca27-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ca27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ca27-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="0ca27-106">[out] Ein Zeiger auf die Adresse der einen Klon der `IHostSecurityContext` Objekt erfasst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0ca27-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ca27-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ca27-107">Return Value</span></span>  
  
|<span data-ttu-id="0ca27-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ca27-108">HRESULT</span></span>|<span data-ttu-id="0ca27-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ca27-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ca27-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ca27-110">S_OK</span></span>|<span data-ttu-id="0ca27-111">`Capture` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ca27-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="0ca27-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ca27-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ca27-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0ca27-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ca27-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ca27-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ca27-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0ca27-115">The call timed out.</span></span>|  
|<span data-ttu-id="0ca27-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ca27-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ca27-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0ca27-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ca27-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ca27-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ca27-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0ca27-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ca27-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ca27-120">E_FAIL</span></span>|<span data-ttu-id="0ca27-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0ca27-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ca27-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ca27-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ca27-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0ca27-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ca27-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ca27-124">Remarks</span></span>  
 <span data-ttu-id="0ca27-125">Der Schnittstellenzeiger zurückgegeben, die von `Capture` ist ein Klon des erfassten Kontext.</span><span class="sxs-lookup"><span data-stu-id="0ca27-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="0ca27-126">Wenn diese Informationen über einen Punkt von asynchronem Code verschoben wird, wird seine Lebensdauer von der der Zeiger getrennt für die der Aufruf erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="0ca27-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="0ca27-127">Der ursprüngliche Zeiger kann aus diesem Grund aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="0ca27-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ca27-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ca27-128">Requirements</span></span>  
 <span data-ttu-id="0ca27-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ca27-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ca27-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ca27-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ca27-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0ca27-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ca27-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ca27-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca27-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ca27-133">See also</span></span>

- [<span data-ttu-id="0ca27-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ca27-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="0ca27-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ca27-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
