---
title: IHostMAlloc::DebugAlloc-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 63249f6ce64071ddaa2bb9dff221ae40d924bbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="be87f-102">IHostMAlloc::DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="be87f-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="be87f-103">Fordert an, dass der Host die angegebene Menge des Arbeitsspeichers aus dem Heap reserviert und außerdem nachverfolgt, in dem der Speicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="be87f-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be87f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be87f-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be87f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be87f-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="be87f-106">[in] Die Größe in Bytes, der die aktuelle speicherbelegungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="be87f-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="be87f-107">[in] Eines der [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Werte, der angibt, der Auswirkungen eines zuordnungsfehlers.</span><span class="sxs-lookup"><span data-stu-id="be87f-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="be87f-108">[in] Die Codedatei der zu debuggenden ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="be87f-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="be87f-109">[in] Die Zeilennummer im `pszFileName` , in die Belegung angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="be87f-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="be87f-110">[out] Ein Zeiger auf den reservierten Arbeitsspeicher oder Null, wenn die Anforderung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="be87f-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be87f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="be87f-111">Return Value</span></span>  
  
|<span data-ttu-id="be87f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be87f-112">HRESULT</span></span>|<span data-ttu-id="be87f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be87f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be87f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="be87f-114">S_OK</span></span>|<span data-ttu-id="be87f-115">`DebugAlloc`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be87f-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="be87f-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="be87f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be87f-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="be87f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be87f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="be87f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="be87f-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="be87f-119">The call timed out.</span></span>|  
|<span data-ttu-id="be87f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="be87f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="be87f-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="be87f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="be87f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="be87f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="be87f-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="be87f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="be87f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be87f-124">E_FAIL</span></span>|<span data-ttu-id="be87f-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="be87f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be87f-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="be87f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="be87f-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="be87f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="be87f-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="be87f-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="be87f-129">Es war nicht genügend Arbeitsspeicher verfügbar, um die zuordnungsanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="be87f-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be87f-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be87f-130">Remarks</span></span>  
 <span data-ttu-id="be87f-131">Die CLR ruft einen Schnittstellenzeiger auf eine [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) Instanz durch Aufrufen der [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="be87f-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="be87f-132">`DebugAlloc`die Laufzeit beim Abrufen von Informationen für die Verwendung während des Debuggens Code ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="be87f-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be87f-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be87f-133">Requirements</span></span>  
 <span data-ttu-id="be87f-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be87f-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be87f-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be87f-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be87f-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="be87f-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be87f-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be87f-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be87f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be87f-138">See Also</span></span>  
 [<span data-ttu-id="be87f-139">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be87f-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="be87f-140">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be87f-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
