---
title: IHostMemoryManager-Schnittstelle
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
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b39a43874bc1808928f21e0a35638aae9a99ca8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="7b902-102">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b902-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="7b902-103">Stellt Methoden, mit die die common Language Runtime (CLR) virtueller Arbeitsspeicher Anforderungen über den Host vornehmen können statt der standardmäßigen Win32 virtueller Arbeitsspeicher Funktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="7b902-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b902-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="7b902-104">Methods</span></span>  
  
|<span data-ttu-id="7b902-105">Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-105">Method</span></span>|<span data-ttu-id="7b902-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b902-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b902-107">AcquiredVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="7b902-108">Benachrichtigt den Host, dass die common Language Runtime (CLR) auf den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="7b902-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="7b902-109">CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="7b902-110">Ruft einen Schnittstellenzeiger auf eine [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz, die zum Anfordern von speicherbelegungen aus einem Heap erstellt, die vom Host verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7b902-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="7b902-111">GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="7b902-112">Ruft die Größe des physischen Speichers, der gerade verwendet wird, ab, wie durch den Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="7b902-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="7b902-113">NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="7b902-114">Benachrichtigt den Host, dass die CLR versucht, den angegebenen Arbeitsspeicher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7b902-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="7b902-115">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="7b902-116">Registriert einen Zeiger auf eine Rückruffunktion, die der Host wird aufgerufen, um die CLR über der aktuellen Auslastung des Arbeitsspeichers auf dem Computer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="7b902-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="7b902-117">ReleasedVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="7b902-118">Benachrichtigt den Host, dass die CLR wurde mit den angegebenen Speicher.</span><span class="sxs-lookup"><span data-stu-id="7b902-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="7b902-119">VirtualAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="7b902-120">Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die reserviert oder führt einen Commit für einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7b902-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="7b902-121">VirtualFree-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="7b902-122">Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die frei, Aufhebung der Zusage, oder freigibt und Aufhebung der Zusage eines von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7b902-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="7b902-123">VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="7b902-124">Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die ändert sich der Schutz für einen Bereich der Seiten im virtuellen Adressraum des aufrufenden Prozesses, die ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7b902-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="7b902-125">VirtualQuery-Methode</span><span class="sxs-lookup"><span data-stu-id="7b902-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="7b902-126">Dient als logischer Wrapper für die entsprechenden Win32-Funktion, die Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abruft.</span><span class="sxs-lookup"><span data-stu-id="7b902-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b902-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b902-127">Remarks</span></span>  
 <span data-ttu-id="7b902-128">`IHostMemoryManager`Außerdem bietet Methoden für die CLR, um einen Zeiger über den Arbeitsspeicher auf dem Heap anzufordern und die abzurufenden die Ebene der arbeitsspeicherauslastung im Prozess, durch den Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="7b902-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b902-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b902-129">Requirements</span></span>  
 <span data-ttu-id="7b902-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b902-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b902-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7b902-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b902-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7b902-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b902-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b902-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b902-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b902-134">See Also</span></span>  
 [<span data-ttu-id="7b902-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b902-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="7b902-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7b902-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
