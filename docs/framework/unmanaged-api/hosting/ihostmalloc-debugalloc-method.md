---
title: IHostMAlloc::DebugAlloc-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e089d133374f112dea13e91f9bd571bd2b5af07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796713"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="b4880-102">IHostMAlloc::DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="b4880-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="b4880-103">Fordert an, dass der Host die angegebene Menge des Arbeitsspeichers aus dem Heap reserviert, und zudem nachverfolgen, in dem der Speicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="b4880-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4880-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4880-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4880-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4880-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="b4880-106">[in] Die Größe des die aktuelle speicherbelegungsanforderung in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b4880-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="b4880-107">[in] Eines der [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Werte, der Sie die Auswirkungen eines zuordnungsfehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="b4880-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="b4880-108">[in] Die Codedatei der debuggten, ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="b4880-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="b4880-109">[in] Die Zeilennummer im `pszFileName` , in denen die Belegung angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="b4880-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="b4880-110">[out] Ein Zeiger auf den zugeordneten Arbeitsspeicher oder Null, wenn die Anforderung konnte nicht abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="b4880-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4880-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4880-111">Return Value</span></span>  
  
|<span data-ttu-id="b4880-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4880-112">HRESULT</span></span>|<span data-ttu-id="b4880-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4880-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4880-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4880-114">S_OK</span></span>|<span data-ttu-id="b4880-115">`DebugAlloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4880-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="b4880-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4880-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4880-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b4880-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4880-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4880-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4880-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b4880-119">The call timed out.</span></span>|  
|<span data-ttu-id="b4880-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4880-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4880-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b4880-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4880-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4880-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4880-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="b4880-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4880-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4880-124">E_FAIL</span></span>|<span data-ttu-id="b4880-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b4880-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4880-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4880-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4880-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b4880-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b4880-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b4880-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b4880-129">Es war nicht genügend Arbeitsspeicher verfügbar, um die Anforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b4880-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4880-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4880-130">Remarks</span></span>  
 <span data-ttu-id="b4880-131">Die CLR ruft einen Schnittstellenzeiger auf ein [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz durch Aufrufen der [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b4880-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="b4880-132">`DebugAlloc` ermöglicht der Runtime beim Abrufen von Informationen zur Verwendung während des Debuggens Code.</span><span class="sxs-lookup"><span data-stu-id="b4880-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4880-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4880-133">Requirements</span></span>  
 <span data-ttu-id="b4880-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4880-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4880-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4880-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4880-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b4880-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4880-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4880-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4880-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4880-138">See also</span></span>

- [<span data-ttu-id="b4880-139">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4880-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="b4880-140">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4880-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
