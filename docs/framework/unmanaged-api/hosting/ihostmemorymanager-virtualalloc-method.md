---
title: IHostMemoryManager::VirtualAlloc-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 761958c44ad374d522a52826929e320e65957ffa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="bd89b-102">IHostMemoryManager::VirtualAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="bd89b-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="bd89b-103">Dient als logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="bd89b-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="bd89b-104">Die Win32-Implementierung von `VirtualAlloc` reserviert oder führt einen Commit für einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="bd89b-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd89b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd89b-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd89b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd89b-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="bd89b-107">[in] Ein Zeiger auf die Startadresse des Bereichs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd89b-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="bd89b-108">[in] Die Größe in Bytes, der Region.</span><span class="sxs-lookup"><span data-stu-id="bd89b-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="bd89b-109">[in] Der Typ der speicherbelegung.</span><span class="sxs-lookup"><span data-stu-id="bd89b-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="bd89b-110">[in] Arbeitsspeicherschutz für den Bereich der Seiten, die zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd89b-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="bd89b-111">[in] Ein [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) Wert, der die Auswirkungen eines zuordnungsfehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="bd89b-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="bd89b-112">[out] Ein Zeiger auf die Startadresse des belegten Arbeitsspeichers oder Null, wenn die Anforderung nicht erfüllt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="bd89b-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd89b-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bd89b-113">Return Value</span></span>  
  
|<span data-ttu-id="bd89b-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd89b-114">HRESULT</span></span>|<span data-ttu-id="bd89b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd89b-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd89b-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd89b-116">S_OK</span></span>|<span data-ttu-id="bd89b-117">`VirtualAlloc`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd89b-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="bd89b-118">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="bd89b-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd89b-119">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="bd89b-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd89b-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd89b-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd89b-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bd89b-121">The call timed out.</span></span>|  
|<span data-ttu-id="bd89b-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd89b-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd89b-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="bd89b-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd89b-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd89b-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd89b-125">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="bd89b-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd89b-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd89b-126">E_FAIL</span></span>|<span data-ttu-id="bd89b-127">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bd89b-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd89b-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="bd89b-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd89b-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="bd89b-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bd89b-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bd89b-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="bd89b-131">Es war nicht genügend Arbeitsspeicher verfügbar, um die zuordnungsanforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="bd89b-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd89b-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd89b-132">Remarks</span></span>  
 <span data-ttu-id="bd89b-133">Sie reservieren eine Region im Adressraum des Prozesses, durch den Aufruf `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="bd89b-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="bd89b-134">Die `pAddress` Parameter enthält die Startadresse des Speicherblocks werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bd89b-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="bd89b-135">Dieser Parameter wird in der Regel festgelegt auf Null.</span><span class="sxs-lookup"><span data-stu-id="bd89b-135">This parameter is typically set to null.</span></span> <span data-ttu-id="bd89b-136">Das Betriebssystem zeichnet freie Adressbereiche für den Prozess verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bd89b-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="bd89b-137">Ein `pAddress` Null-Wert weist das System an passenden Bereich zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="bd89b-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="bd89b-138">Alternativ können Sie eine bestimmte Startadresse für den Speicherblock bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bd89b-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="bd89b-139">In beiden Fällen wird die Output-Parameter `ppMem` wird als Zeiger auf den zugeordneten Speicher zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bd89b-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="bd89b-140">Die Funktion selbst gibt einen HRESULT-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="bd89b-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="bd89b-141">Die Win32 `VirtualAlloc` Funktion verfügt nicht über eine `ppMem` Parameter, und gibt stattdessen den Zeiger auf den belegten Speicher zurück.</span><span class="sxs-lookup"><span data-stu-id="bd89b-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="bd89b-142">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="bd89b-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd89b-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd89b-143">Requirements</span></span>  
 <span data-ttu-id="bd89b-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd89b-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd89b-145">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd89b-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd89b-146">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bd89b-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd89b-147">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd89b-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd89b-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd89b-148">See Also</span></span>  
 [<span data-ttu-id="bd89b-149">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd89b-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
