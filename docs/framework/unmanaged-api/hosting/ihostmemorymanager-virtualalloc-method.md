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
ms.openlocfilehash: a2deabc5f1c7ea0f42b6d8ec3944d984854ae571
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731279"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="f1630-102">IHostMemoryManager::VirtualAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="f1630-102">IHostMemoryManager::VirtualAlloc Method</span></span>

<span data-ttu-id="f1630-103">Dient als logischer Wrapper für die entsprechende Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="f1630-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="f1630-104">Die Win32-Implementierung von `VirtualAlloc` reserviert oder übergibt einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="f1630-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1630-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1630-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f1630-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1630-106">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="f1630-107">in Ein Zeiger auf die Startadresse des zuzuordnenden Bereichs.</span><span class="sxs-lookup"><span data-stu-id="f1630-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="f1630-108">in Die Größe (in Bytes) der Region.</span><span class="sxs-lookup"><span data-stu-id="f1630-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="f1630-109">in Der Typ der Speicher Belegung.</span><span class="sxs-lookup"><span data-stu-id="f1630-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="f1630-110">in Arbeitsspeicher Schutz für den Bereich von Seiten, die zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f1630-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="f1630-111">in Ein [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) -Wert, der die Auswirkung eines Zuordnungs Fehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="f1630-111">[in] An [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="f1630-112">vorgenommen Ein Zeiger auf die Startadresse des zugeordneten Speichers oder NULL, wenn die Anforderung nicht erfüllt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="f1630-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1630-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f1630-113">Return Value</span></span>  
  
|<span data-ttu-id="f1630-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1630-114">HRESULT</span></span>|<span data-ttu-id="f1630-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f1630-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1630-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1630-116">S_OK</span></span>|<span data-ttu-id="f1630-117">`VirtualAlloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1630-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="f1630-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f1630-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f1630-119">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f1630-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f1630-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f1630-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f1630-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f1630-121">The call timed out.</span></span>|  
|<span data-ttu-id="f1630-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f1630-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f1630-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f1630-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f1630-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f1630-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f1630-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f1630-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f1630-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f1630-126">E_FAIL</span></span>|<span data-ttu-id="f1630-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f1630-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f1630-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="f1630-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f1630-129">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f1630-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f1630-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f1630-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f1630-131">Zum Abschluss der Zuordnungs Anforderung war nicht genügend Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1630-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1630-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1630-132">Remarks</span></span>  

 <span data-ttu-id="f1630-133">Sie reservieren eine Region im Adressraum Ihres Prozesses, indem Sie aufrufen `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="f1630-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="f1630-134">Der- `pAddress` Parameter enthält die Anfangsadresse des gewünschten Speicherblocks.</span><span class="sxs-lookup"><span data-stu-id="f1630-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="f1630-135">Dieser Parameter ist in der Regel auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f1630-135">This parameter is typically set to null.</span></span> <span data-ttu-id="f1630-136">Das Betriebssystem speichert einen Datensatz mit freien Adressbereichen, die für Ihren Prozess verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f1630-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="f1630-137">`pAddress`Der Wert NULL weist das System an, die Region zu reservieren, wo Sie für Sie geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f1630-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="f1630-138">Alternativ können Sie eine bestimmte Startadresse für den Speicherblock bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f1630-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="f1630-139">In beiden Fällen wird der Output-Parameter `ppMem` als Zeiger auf den zugeordneten Speicher zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1630-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="f1630-140">Die Funktion selbst gibt einen HRESULT-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="f1630-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="f1630-141">Die Win32 `VirtualAlloc` -Funktion verfügt über keinen `ppMem` -Parameter und gibt stattdessen den Zeiger auf den zugeordneten Arbeitsspeicher zurück.</span><span class="sxs-lookup"><span data-stu-id="f1630-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="f1630-142">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="f1630-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1630-143">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1630-143">Requirements</span></span>  

 <span data-ttu-id="f1630-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1630-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1630-145">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f1630-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1630-146">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f1630-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1630-147">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1630-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1630-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1630-148">See also</span></span>

- [<span data-ttu-id="f1630-149">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1630-149">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
