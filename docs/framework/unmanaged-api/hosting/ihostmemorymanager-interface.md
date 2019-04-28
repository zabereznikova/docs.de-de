---
title: IHostMemoryManager-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f34ed1796f6fa411d31fca83baeff693f85d70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760174"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="50a46-102">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50a46-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="50a46-103">Enthält Methoden, mit denen die common Language Runtime (CLR) zum virtuellen Arbeitsspeicher Anforderungen über den Host, anstelle der Win32-Standardfunktionen der virtuellen Speicher an.</span><span class="sxs-lookup"><span data-stu-id="50a46-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50a46-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="50a46-104">Methods</span></span>  
  
|<span data-ttu-id="50a46-105">Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-105">Method</span></span>|<span data-ttu-id="50a46-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50a46-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50a46-107">AcquiredVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="50a46-108">Benachrichtigt den Host aus, die common Language Runtime (CLR) auf den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="50a46-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="50a46-109">CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="50a46-110">Ruft einen Schnittstellenzeiger auf ein [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz, die zum Anfordern der speicherbelegung aus einem Heap erstellt, die vom Host verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50a46-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="50a46-111">GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="50a46-112">Ruft die Menge des physischen Speichers, der gerade verwendet wird, ab, wie durch den Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="50a46-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="50a46-113">NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="50a46-114">Benachrichtigt den Host, dass die CLR versucht, den angegebenen Speicher zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="50a46-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="50a46-115">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="50a46-116">Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die CLR über die aktuelle Auslastung des Arbeitsspeichers auf dem Computer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="50a46-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="50a46-117">ReleasedVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="50a46-118">Benachrichtigt den Host, dass die CLR wurde mit den angegebenen Speicher.</span><span class="sxs-lookup"><span data-stu-id="50a46-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="50a46-119">VirtualAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="50a46-120">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion, die reserviert oder übergibt einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="50a46-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="50a46-121">VirtualFree-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="50a46-122">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion, die Versionen, bewirkt, oder frei und Aufhebung der Zusage eines der Seiten, die innerhalb des virtuellen Adressraums des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="50a46-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="50a46-123">VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="50a46-124">Dient als ein logischer Wrapper für die entsprechende Win32-Funktion, die den Schutz in einem Bereich von Seiten mit Commit in der virtuelle Adressraum des aufrufenden Prozesses geändert.</span><span class="sxs-lookup"><span data-stu-id="50a46-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="50a46-125">VirtualQuery-Methode</span><span class="sxs-lookup"><span data-stu-id="50a46-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="50a46-126">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion, die Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abgerufen.</span><span class="sxs-lookup"><span data-stu-id="50a46-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50a46-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50a46-127">Remarks</span></span>  
 <span data-ttu-id="50a46-128">`IHostMemoryManager` Außerdem bietet Methoden für die CLR einen Zeiger über die speicheranforderungen auf dem Heap zu machen, sowie zum Abrufen der Ebene der arbeitsspeicherauslastung im Prozess zu erhalten, wie durch den Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="50a46-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a46-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50a46-129">Requirements</span></span>  
 <span data-ttu-id="50a46-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50a46-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a46-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50a46-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50a46-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50a46-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50a46-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a46-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a46-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50a46-134">See also</span></span>

- [<span data-ttu-id="50a46-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50a46-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="50a46-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="50a46-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
