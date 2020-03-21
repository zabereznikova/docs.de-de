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
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176304"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="a9c79-102">IHostMAlloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="a9c79-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="a9c79-103">Fordert an, dass der Host die angegebene Speichermenge aus dem Heap zuweist.</span><span class="sxs-lookup"><span data-stu-id="a9c79-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9c79-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9c79-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9c79-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="a9c79-106">[in] Die Größe der aktuellen Speicherzuweisungsanforderung in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a9c79-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="a9c79-107">[in] Einer der [EMemoryCriticalLevel-Werte,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) der die Auswirkungen eines Zuordnungsfehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="a9c79-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="a9c79-108">[out] Ein Zeiger auf den zugewiesenen Speicher oder NULL, wenn die Anforderung nicht abgeschlossen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="a9c79-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9c79-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a9c79-109">Return Value</span></span>  
  
|<span data-ttu-id="a9c79-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9c79-110">HRESULT</span></span>|<span data-ttu-id="a9c79-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9c79-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9c79-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9c79-112">S_OK</span></span>|<span data-ttu-id="a9c79-113">`Alloc`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9c79-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="a9c79-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9c79-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9c79-115">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a9c79-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9c79-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9c79-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9c79-117">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="a9c79-117">The call timed out.</span></span>|  
|<span data-ttu-id="a9c79-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9c79-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9c79-119">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="a9c79-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9c79-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9c79-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9c79-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a9c79-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9c79-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9c79-122">E_FAIL</span></span>|<span data-ttu-id="a9c79-123">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a9c79-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9c79-124">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9c79-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9c79-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a9c79-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a9c79-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a9c79-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a9c79-127">Es war nicht genügend Arbeitsspeicher verfügbar, um die Zuweisungsanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a9c79-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9c79-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a9c79-128">Remarks</span></span>  
 <span data-ttu-id="a9c79-129">Die CLR ruft einen Schnittstellenzeiger auf eine `IHostMalloc` Instanz ab, indem sie die [IHostMemoryManager::CreateMalloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) aufruft.</span><span class="sxs-lookup"><span data-stu-id="a9c79-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9c79-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a9c79-130">Requirements</span></span>  
 <span data-ttu-id="a9c79-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9c79-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c79-132">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9c79-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9c79-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a9c79-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9c79-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c79-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c79-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9c79-135">See also</span></span>

- [<span data-ttu-id="a9c79-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9c79-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="a9c79-137">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9c79-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
