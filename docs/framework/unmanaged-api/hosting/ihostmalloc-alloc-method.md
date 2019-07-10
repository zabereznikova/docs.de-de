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
ms.openlocfilehash: e38d1f3cfe78b7f47a37c12c84282196f4385fbb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780750"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="53790-102">IHostMAlloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="53790-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="53790-103">Fordert an, dass der Host die angegebene Arbeitsspeichermenge aus dem Heap zuordnen.</span><span class="sxs-lookup"><span data-stu-id="53790-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53790-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53790-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53790-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53790-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="53790-106">[in] Die Größe des die aktuelle speicherbelegungsanforderung in Bytes.</span><span class="sxs-lookup"><span data-stu-id="53790-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="53790-107">[in] Eines der [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Werte, der Sie die Auswirkungen eines zuordnungsfehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="53790-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="53790-108">[out] Ein Zeiger auf den zugeordneten Arbeitsspeicher oder Null, wenn die Anforderung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="53790-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53790-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="53790-109">Return Value</span></span>  
  
|<span data-ttu-id="53790-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53790-110">HRESULT</span></span>|<span data-ttu-id="53790-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53790-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53790-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="53790-112">S_OK</span></span>|<span data-ttu-id="53790-113">`Alloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53790-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="53790-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53790-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53790-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="53790-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53790-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53790-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53790-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="53790-117">The call timed out.</span></span>|  
|<span data-ttu-id="53790-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53790-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53790-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="53790-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53790-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53790-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53790-121">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="53790-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53790-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53790-122">E_FAIL</span></span>|<span data-ttu-id="53790-123">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="53790-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53790-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53790-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53790-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="53790-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="53790-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="53790-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="53790-127">Es war nicht genügend Arbeitsspeicher verfügbar, um die Anforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="53790-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53790-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53790-128">Remarks</span></span>  
 <span data-ttu-id="53790-129">Die CLR ruft einen Schnittstellenzeiger auf ein `IHostMalloc` -Instanz durch Aufrufen der [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="53790-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53790-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53790-130">Requirements</span></span>  
 <span data-ttu-id="53790-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53790-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53790-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53790-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53790-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="53790-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53790-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53790-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53790-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53790-135">See also</span></span>

- [<span data-ttu-id="53790-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53790-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="53790-137">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53790-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
