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
ms.openlocfilehash: c8b4d4c7edec47ab4acaae2a5cd93ad474612063
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855542"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="08f31-102">IHostSecurityContext::Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="08f31-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="08f31-103">Ruft einen Klon der [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) -Instanz ab, die von einem [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)-Befehl zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="08f31-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08f31-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08f31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08f31-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="08f31-106">vorgenommen Ein Zeiger auf die Adresse eines Klons des `IHostSecurityContext` zu erfassenden Objekts.</span><span class="sxs-lookup"><span data-stu-id="08f31-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08f31-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08f31-107">Return Value</span></span>  
  
|<span data-ttu-id="08f31-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08f31-108">HRESULT</span></span>|<span data-ttu-id="08f31-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08f31-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08f31-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08f31-110">S_OK</span></span>|<span data-ttu-id="08f31-111">`Capture`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08f31-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="08f31-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08f31-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08f31-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="08f31-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08f31-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08f31-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08f31-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="08f31-115">The call timed out.</span></span>|  
|<span data-ttu-id="08f31-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08f31-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08f31-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="08f31-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08f31-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08f31-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08f31-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="08f31-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08f31-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08f31-120">E_FAIL</span></span>|<span data-ttu-id="08f31-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08f31-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08f31-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08f31-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08f31-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="08f31-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08f31-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08f31-124">Remarks</span></span>  
 <span data-ttu-id="08f31-125">Der von `Capture` zurückgegebene Schnittstellen Zeiger ist ein Klon des erfassten Kontexts.</span><span class="sxs-lookup"><span data-stu-id="08f31-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="08f31-126">Wenn diese Informationen über einen asynchronen Codepunkt verschoben werden, wird die Lebensdauer von der des Zeigers getrennt, für den der-Befehl durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="08f31-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="08f31-127">Der ursprüngliche Zeiger kann daher freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="08f31-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08f31-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08f31-128">Requirements</span></span>  
 <span data-ttu-id="08f31-129">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08f31-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08f31-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08f31-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08f31-131">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="08f31-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08f31-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08f31-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f31-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08f31-133">See also</span></span>

- [<span data-ttu-id="08f31-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08f31-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="08f31-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08f31-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
