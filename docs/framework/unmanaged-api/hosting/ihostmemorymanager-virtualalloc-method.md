---
title: IHostMemoryManager::VirtualAlloc-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a0764cb212a95412a4dcf9455b7648ee863951e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767664"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="0f772-102">IHostMemoryManager::VirtualAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="0f772-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="0f772-103">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="0f772-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="0f772-104">Die Win32-Implementierung von `VirtualAlloc` reserviert oder übergibt einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="0f772-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f772-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f772-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f772-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f772-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="0f772-107">[in] Ein Zeiger auf die Startadresse des Bereichs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0f772-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="0f772-108">[in] Die Größe in Bytes des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="0f772-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="0f772-109">[in] Der Typ der speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="0f772-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="0f772-110">[in] Arbeitsspeicherschutz für den Bereich der Seiten, die zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="0f772-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="0f772-111">[in] Ein [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Wert, der die Auswirkungen eines zuordnungsfehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="0f772-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="0f772-112">[out] Zeiger auf die Startadresse des zugeordneten Speichers oder Null, wenn die Anforderung nicht erfüllt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="0f772-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f772-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f772-113">Return Value</span></span>  
  
|<span data-ttu-id="0f772-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f772-114">HRESULT</span></span>|<span data-ttu-id="0f772-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f772-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f772-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f772-116">S_OK</span></span>|<span data-ttu-id="0f772-117">`VirtualAlloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0f772-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="0f772-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f772-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f772-119">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f772-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f772-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f772-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f772-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f772-121">The call timed out.</span></span>|  
|<span data-ttu-id="0f772-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f772-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f772-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0f772-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f772-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f772-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f772-125">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0f772-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f772-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f772-126">E_FAIL</span></span>|<span data-ttu-id="0f772-127">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f772-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f772-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f772-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f772-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0f772-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0f772-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0f772-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0f772-131">Es war nicht genügend Arbeitsspeicher verfügbar, um die Anforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0f772-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f772-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f772-132">Remarks</span></span>  
 <span data-ttu-id="0f772-133">Reservieren Sie eine Region in den Adressraum des Prozesses durch den Aufruf `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="0f772-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="0f772-134">Die `pAddress` Parameter enthält die Startadresse des Speicherblocks werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f772-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="0f772-135">Dieser Parameter wird in der Regel festgelegt auf Null.</span><span class="sxs-lookup"><span data-stu-id="0f772-135">This parameter is typically set to null.</span></span> <span data-ttu-id="0f772-136">Das Betriebssystem zeichnet freie Adressbereiche, die für Ihren Prozess zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0f772-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="0f772-137">Ein `pAddress` Null-Wert weist das System an die Region zu reservieren, wo sie Ihr als angemessen erscheint.</span><span class="sxs-lookup"><span data-stu-id="0f772-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="0f772-138">Alternativ können Sie eine bestimmte Startadresse für den Speicherblock bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f772-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="0f772-139">In beiden Fällen den Ausgabeparameter `ppMem` wird als Zeiger auf den zugeordneten Speicher zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0f772-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="0f772-140">Die Funktion selbst gibt einen HRESULT-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="0f772-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="0f772-141">Die Win32 `VirtualAlloc` Funktion verfügt nicht über eine `ppMem` -Parameter und gibt stattdessen den Zeiger auf den reservierten Speicher zurück.</span><span class="sxs-lookup"><span data-stu-id="0f772-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="0f772-142">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="0f772-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f772-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f772-143">Requirements</span></span>  
 <span data-ttu-id="0f772-144">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f772-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f772-145">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f772-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f772-146">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f772-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f772-147">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f772-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f772-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f772-148">See also</span></span>

- [<span data-ttu-id="0f772-149">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f772-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
