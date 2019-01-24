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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17673fb3684747f42556caef4ea54db050eef56e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696180"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="9063f-102">IHostMemoryManager::VirtualFree-Methode</span><span class="sxs-lookup"><span data-stu-id="9063f-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="9063f-103">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="9063f-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="9063f-104">Die Win32-Implementierung von `VirtualFree` frei, das bewirkt, oder das frei und Aufhebung der Zusage eines der Seiten, die innerhalb des virtuellen Adressraums des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="9063f-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9063f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9063f-105">Syntax</span></span>  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9063f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9063f-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="9063f-107">[in] Ein Zeiger auf die Basisadresse der Seiten des virtuellen Speichers freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9063f-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="9063f-108">[in] Die Größe in Bytes des Bereichs, der freigegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="9063f-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="9063f-109">[in] Der Typ des Vorgangs freigegeben.</span><span class="sxs-lookup"><span data-stu-id="9063f-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9063f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9063f-110">Return Value</span></span>  
  
|<span data-ttu-id="9063f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9063f-111">HRESULT</span></span>|<span data-ttu-id="9063f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9063f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9063f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9063f-113">S_OK</span></span>|<span data-ttu-id="9063f-114">`VirtualFree` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9063f-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="9063f-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9063f-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9063f-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9063f-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9063f-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9063f-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9063f-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9063f-118">The call timed out.</span></span>|  
|<span data-ttu-id="9063f-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9063f-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9063f-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9063f-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9063f-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9063f-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9063f-122">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9063f-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9063f-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9063f-123">E_FAIL</span></span>|<span data-ttu-id="9063f-124">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9063f-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9063f-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9063f-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9063f-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9063f-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9063f-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="9063f-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="9063f-128">Es wurde versucht, um Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="9063f-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9063f-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9063f-129">Remarks</span></span>  
 <span data-ttu-id="9063f-130">`VirtualFree` Gibt virtuelle Arbeitsspeicherseiten zugeordneten der `lpAddress` Parameter durch einen früheren Aufruf der [IHostMemoryManager:: VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="9063f-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="9063f-131">Versuche, Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde, sollte HOST_E_INVALIDOPERATION zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9063f-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="9063f-132">Die Semantik ist identisch mit denen der Win32-Implementierung von `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="9063f-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="9063f-133">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="9063f-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9063f-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9063f-134">Requirements</span></span>  
 <span data-ttu-id="9063f-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9063f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9063f-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9063f-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9063f-137">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9063f-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9063f-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9063f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9063f-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9063f-139">See also</span></span>
- [<span data-ttu-id="9063f-140">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9063f-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="9063f-141">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9063f-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
