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
ms.openlocfilehash: e1df31ed8b652837a33b360b1378f99e6800cbea
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501520"
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="3067e-102">IHostSecurityContext::Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="3067e-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="3067e-103">Ruft einen Klon der [IHostSecurityContext](ihostsecuritycontext-interface.md) -Instanz ab, die von einem [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md)-Befehl zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3067e-103">Gets a clone of the [IHostSecurityContext](ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3067e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3067e-104">Syntax</span></span>  
  
```cpp
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3067e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3067e-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="3067e-106">vorgenommen Ein Zeiger auf die Adresse eines Klons des `IHostSecurityContext` zu erfassenden Objekts.</span><span class="sxs-lookup"><span data-stu-id="3067e-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3067e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3067e-107">Return Value</span></span>  
  
|<span data-ttu-id="3067e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3067e-108">HRESULT</span></span>|<span data-ttu-id="3067e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3067e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3067e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3067e-110">S_OK</span></span>|<span data-ttu-id="3067e-111">`Capture`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3067e-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="3067e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3067e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3067e-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3067e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3067e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3067e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3067e-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="3067e-115">The call timed out.</span></span>|  
|<span data-ttu-id="3067e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3067e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3067e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3067e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3067e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3067e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3067e-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="3067e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3067e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3067e-120">E_FAIL</span></span>|<span data-ttu-id="3067e-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3067e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3067e-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="3067e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3067e-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3067e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3067e-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3067e-124">Remarks</span></span>  
 <span data-ttu-id="3067e-125">Der von zurückgegebene Schnittstellen Zeiger `Capture` ist ein Klon des erfassten Kontexts.</span><span class="sxs-lookup"><span data-stu-id="3067e-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="3067e-126">Wenn diese Informationen über einen asynchronen Codepunkt verschoben werden, wird die Lebensdauer von der des Zeigers getrennt, für den der-Befehl durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3067e-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="3067e-127">Der ursprüngliche Zeiger kann daher freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3067e-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3067e-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3067e-128">Requirements</span></span>  
 <span data-ttu-id="3067e-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3067e-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3067e-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3067e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3067e-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3067e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3067e-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3067e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3067e-133">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="3067e-133">See also</span></span>

- [<span data-ttu-id="3067e-134">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3067e-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="3067e-135">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3067e-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
