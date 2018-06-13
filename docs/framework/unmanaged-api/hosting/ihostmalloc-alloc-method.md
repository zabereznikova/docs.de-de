---
title: IHostMAlloc::Alloc-Methode
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d67704aae80113bd41df5ea38acf2a794aacbac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439045"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="3f177-102">IHostMAlloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="3f177-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="3f177-103">Fordert an, dass der Host der angegebene Speichermenge aus dem Heap belegt.</span><span class="sxs-lookup"><span data-stu-id="3f177-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f177-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f177-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f177-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f177-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="3f177-106">[in] Die Größe in Bytes, der die aktuelle speicherbelegungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="3f177-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="3f177-107">[in] Eines der [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Werte, der angibt, der Auswirkungen eines zuordnungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="3f177-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="3f177-108">[out] Ein Zeiger auf den reservierten Arbeitsspeicher oder Null, wenn die Anforderung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="3f177-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f177-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3f177-109">Return Value</span></span>  
  
|<span data-ttu-id="3f177-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f177-110">HRESULT</span></span>|<span data-ttu-id="3f177-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3f177-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f177-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f177-112">S_OK</span></span>|<span data-ttu-id="3f177-113">`Alloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3f177-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="3f177-114">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="3f177-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f177-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3f177-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f177-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f177-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f177-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3f177-117">The call timed out.</span></span>|  
|<span data-ttu-id="3f177-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f177-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f177-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3f177-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f177-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f177-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f177-121">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3f177-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3f177-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f177-122">E_FAIL</span></span>|<span data-ttu-id="3f177-123">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3f177-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f177-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="3f177-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f177-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3f177-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3f177-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3f177-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3f177-127">Es war nicht genügend Arbeitsspeicher verfügbar, um die zuordnungsanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3f177-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f177-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f177-128">Remarks</span></span>  
 <span data-ttu-id="3f177-129">Die CLR ruft einen Schnittstellenzeiger auf eine `IHostMalloc` Instanz durch Aufrufen der [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="3f177-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f177-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3f177-130">Requirements</span></span>  
 <span data-ttu-id="3f177-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f177-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f177-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f177-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f177-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3f177-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f177-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f177-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f177-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f177-135">See Also</span></span>  
 [<span data-ttu-id="3f177-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f177-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="3f177-137">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f177-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
