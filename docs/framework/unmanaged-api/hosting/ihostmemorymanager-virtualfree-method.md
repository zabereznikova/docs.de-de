---
title: IHostMemoryManager::VirtualFree-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
ms.openlocfilehash: be006afaf5966aa4e6d11c73b92004d676c97c7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731266"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="1cc74-102">IHostMemoryManager::VirtualFree-Methode</span><span class="sxs-lookup"><span data-stu-id="1cc74-102">IHostMemoryManager::VirtualFree Method</span></span>

<span data-ttu-id="1cc74-103">Dient als logischer Wrapper für die entsprechende Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="1cc74-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="1cc74-104">Die Win32-Implementierung von `VirtualFree` Releases, decommitten oder gibt einen Seitenbereich innerhalb des virtuellen Adressraums des aufrufenden Prozesses aus.</span><span class="sxs-lookup"><span data-stu-id="1cc74-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc74-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1cc74-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cc74-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1cc74-106">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="1cc74-107">in Ein Zeiger auf die Basisadresse der frei zulegenden virtuellen Speicherseiten.</span><span class="sxs-lookup"><span data-stu-id="1cc74-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="1cc74-108">in Die Größe des freigegebenen Bereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="1cc74-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="1cc74-109">in Der Typ der Freigabe Operation.</span><span class="sxs-lookup"><span data-stu-id="1cc74-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cc74-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1cc74-110">Return Value</span></span>  
  
|<span data-ttu-id="1cc74-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1cc74-111">HRESULT</span></span>|<span data-ttu-id="1cc74-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1cc74-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1cc74-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1cc74-113">S_OK</span></span>|<span data-ttu-id="1cc74-114">`VirtualFree` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1cc74-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="1cc74-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1cc74-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1cc74-116">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1cc74-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1cc74-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1cc74-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1cc74-118">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1cc74-118">The call timed out.</span></span>|  
|<span data-ttu-id="1cc74-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1cc74-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1cc74-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1cc74-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1cc74-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1cc74-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1cc74-122">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1cc74-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1cc74-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1cc74-123">E_FAIL</span></span>|<span data-ttu-id="1cc74-124">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1cc74-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1cc74-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="1cc74-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1cc74-126">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1cc74-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1cc74-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1cc74-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1cc74-128">Es wurde versucht, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="1cc74-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cc74-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1cc74-129">Remarks</span></span>  

 <span data-ttu-id="1cc74-130">`VirtualFree` gibt `lpAddress` durch einen früheren Aufrufen der [IHostMemoryManager:: virtualbelegc](ihostmemorymanager-virtualalloc-method.md) -Funktion virtuelle Speicherseiten frei, die dem-Parameter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1cc74-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="1cc74-131">Versuche, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde, sollten HOST_E_INVALIDOPERATION zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1cc74-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="1cc74-132">Die Semantik ist identisch mit denen der Win32-Implementierung von `VirtualFree` .</span><span class="sxs-lookup"><span data-stu-id="1cc74-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="1cc74-133">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="1cc74-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc74-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1cc74-134">Requirements</span></span>  

 <span data-ttu-id="1cc74-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cc74-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc74-136">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1cc74-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cc74-137">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1cc74-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cc74-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cc74-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc74-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cc74-139">See also</span></span>

- [<span data-ttu-id="1cc74-140">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1cc74-140">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="1cc74-141">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1cc74-141">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
