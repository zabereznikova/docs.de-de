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
ms.openlocfilehash: 6f58e2290afa166d48306c0bbb50edd1df36888b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804647"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="f0643-102">IHostMAlloc::Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="f0643-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="f0643-103">Fordert an, dass der Host die angegebene Arbeitsspeicher Menge aus dem Heap zuweist.</span><span class="sxs-lookup"><span data-stu-id="f0643-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0643-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0643-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0643-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0643-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="f0643-106">in Die Größe der aktuellen Speicher Belegungs Anforderung in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f0643-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="f0643-107">in Einer der [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) -Werte, der die Auswirkung eines Zuordnungs Fehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="f0643-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="f0643-108">vorgenommen Ein Zeiger auf den zugeordneten Arbeitsspeicher oder NULL, wenn die Anforderung nicht abgeschlossen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="f0643-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0643-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0643-109">Return Value</span></span>  
  
|<span data-ttu-id="f0643-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0643-110">HRESULT</span></span>|<span data-ttu-id="f0643-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0643-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0643-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0643-112">S_OK</span></span>|<span data-ttu-id="f0643-113">`Alloc`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0643-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="f0643-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0643-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0643-115">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f0643-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f0643-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0643-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0643-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f0643-117">The call timed out.</span></span>|  
|<span data-ttu-id="f0643-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0643-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0643-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f0643-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0643-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0643-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0643-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f0643-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0643-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0643-122">E_FAIL</span></span>|<span data-ttu-id="f0643-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f0643-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0643-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="f0643-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0643-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f0643-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f0643-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f0643-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f0643-127">Zum Abschluss der Zuordnungs Anforderung war nicht genügend Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f0643-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0643-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0643-128">Remarks</span></span>  
 <span data-ttu-id="f0643-129">Die CLR ruft einen Schnittstellen Zeiger auf eine-Instanz ab, `IHostMalloc` indem die [IHostMemoryManager:: createmzuzugsmethode](ihostmemorymanager-createmalloc-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f0643-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0643-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0643-130">Requirements</span></span>  
 <span data-ttu-id="f0643-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0643-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0643-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f0643-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0643-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f0643-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0643-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0643-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0643-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0643-135">See also</span></span>

- [<span data-ttu-id="f0643-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0643-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="f0643-137">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0643-137">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
