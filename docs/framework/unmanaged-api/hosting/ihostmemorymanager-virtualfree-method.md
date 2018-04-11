---
title: IHostMemoryManager::VirtualFree-Methode
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
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
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 663c01d7e4b551ecf18bdd85a63aefc43f9750e2
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="5c92d-102">IHostMemoryManager::VirtualFree-Methode</span><span class="sxs-lookup"><span data-stu-id="5c92d-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="5c92d-103">Dient als logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="5c92d-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="5c92d-104">Die Win32-Implementierung von `VirtualFree` frei, Aufhebung der Zusage, oder freigibt und Aufhebung der Zusage eines von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="5c92d-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c92d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c92d-105">Syntax</span></span>  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c92d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c92d-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="5c92d-107">[in] Ein Zeiger auf die Basisadresse der Seiten virtueller Arbeitsspeicher freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5c92d-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="5c92d-108">[in] Die Größe in Bytes, des Bereichs, der freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5c92d-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="5c92d-109">[in] Der Typ des Vorgangs freigegeben.</span><span class="sxs-lookup"><span data-stu-id="5c92d-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c92d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5c92d-110">Return Value</span></span>  
  
|<span data-ttu-id="5c92d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c92d-111">HRESULT</span></span>|<span data-ttu-id="5c92d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c92d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c92d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c92d-113">S_OK</span></span>|<span data-ttu-id="5c92d-114">`VirtualFree` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5c92d-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="5c92d-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5c92d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5c92d-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5c92d-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5c92d-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5c92d-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5c92d-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5c92d-118">The call timed out.</span></span>|  
|<span data-ttu-id="5c92d-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5c92d-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5c92d-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5c92d-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5c92d-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5c92d-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5c92d-122">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="5c92d-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5c92d-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c92d-123">E_FAIL</span></span>|<span data-ttu-id="5c92d-124">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5c92d-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c92d-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="5c92d-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5c92d-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5c92d-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5c92d-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="5c92d-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="5c92d-128">Es wurde versucht, um Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c92d-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c92d-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5c92d-129">Remarks</span></span>  
 <span data-ttu-id="5c92d-130">`VirtualFree` zugeordnete Seiten des virtuellen Speichers freigegeben der `lpAddress` Parameter durch einen früheren Aufruf der [IHostMemoryManager:: VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="5c92d-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="5c92d-131">Versuche, um Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde, sollten HOST_E_INVALIDOPERATION zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5c92d-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="5c92d-132">Die Semantik sind identisch mit denen der Win32-Implementierung von `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="5c92d-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="5c92d-133">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="5c92d-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c92d-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c92d-134">Requirements</span></span>  
 <span data-ttu-id="5c92d-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c92d-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c92d-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c92d-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c92d-137">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5c92d-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c92d-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c92d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c92d-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c92d-139">See Also</span></span>  
 [<span data-ttu-id="5c92d-140">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c92d-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="5c92d-141">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c92d-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
