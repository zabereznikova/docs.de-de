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
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178035"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="5e367-102">IHostMAlloc::DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="5e367-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="5e367-103">Fordert an, dass der Host die angegebene Speichermenge aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Speicher zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="5e367-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e367-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e367-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e367-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e367-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="5e367-106">[in] Die Größe der aktuellen Speicherzuweisungsanforderung in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5e367-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="5e367-107">[in] Einer der [EMemoryCriticalLevel-Werte,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) der die Auswirkungen eines Zuordnungsfehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="5e367-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="5e367-108">[in] Die Codedatei der ausführbaren Datei, die gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="5e367-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="5e367-109">[in] Die Positionsnummer, in `pszFileName` der die Zuordnung angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="5e367-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="5e367-110">[out] Ein Zeiger auf den zugewiesenen Speicher oder NULL, wenn die Anforderung nicht abgeschlossen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="5e367-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e367-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5e367-111">Return Value</span></span>  
  
|<span data-ttu-id="5e367-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e367-112">HRESULT</span></span>|<span data-ttu-id="5e367-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e367-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e367-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e367-114">S_OK</span></span>|<span data-ttu-id="5e367-115">`DebugAlloc`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e367-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="5e367-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e367-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e367-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="5e367-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e367-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e367-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e367-119">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="5e367-119">The call timed out.</span></span>|  
|<span data-ttu-id="5e367-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e367-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e367-121">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="5e367-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e367-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e367-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e367-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="5e367-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e367-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e367-124">E_FAIL</span></span>|<span data-ttu-id="5e367-125">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5e367-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e367-126">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e367-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e367-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5e367-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5e367-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5e367-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5e367-129">Es war nicht genügend Arbeitsspeicher verfügbar, um die Zuweisungsanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="5e367-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e367-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5e367-130">Remarks</span></span>  
 <span data-ttu-id="5e367-131">Die CLR ruft einen Schnittstellenzeiger auf eine [IHostMalloc-Instanz](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) ab, indem sie die [IHostMemoryManager::CreateMalloc-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) aufruft.</span><span class="sxs-lookup"><span data-stu-id="5e367-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="5e367-132">`DebugAlloc`ermöglicht es der Laufzeit, Codedateiinformationen für die Verwendung während des Debuggens abzubekommen.</span><span class="sxs-lookup"><span data-stu-id="5e367-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e367-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5e367-133">Requirements</span></span>  
 <span data-ttu-id="5e367-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e367-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e367-135">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e367-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e367-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5e367-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e367-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e367-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e367-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e367-138">See also</span></span>

- [<span data-ttu-id="5e367-139">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e367-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="5e367-140">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e367-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
