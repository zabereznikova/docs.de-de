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
ms.openlocfilehash: bc05d76795f20d28d6d2899d61dc4674ebfdca8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128647"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="a97bd-102">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a97bd-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="a97bd-103">Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, virtuelle Speicheranforderungen über den Host zu erstellen, statt die standardmäßigen Win32-Funktionen für den virtuellen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a97bd-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a97bd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a97bd-104">Methods</span></span>  
  
|<span data-ttu-id="a97bd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-105">Method</span></span>|<span data-ttu-id="a97bd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a97bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a97bd-107">AcquiredVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="a97bd-108">Benachrichtigt den Host, dass die Common Language Runtime (CLR) den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="a97bd-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="a97bd-109">CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="a97bd-110">Ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz ab, die verwendet wird, um Speicher Belegungen von einem Heap anzufordern, der vom Host erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a97bd-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="a97bd-111">GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="a97bd-112">Ruft die Menge an physischem Arbeitsspeicher ab, die derzeit verwendet wird, wie vom Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a97bd-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="a97bd-113">NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="a97bd-114">Benachrichtigt den Host, dass die CLR versucht, den angegebenen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a97bd-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="a97bd-115">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="a97bd-116">Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die CLR über die aktuelle Arbeitsspeicher Auslastung auf dem Computer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="a97bd-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="a97bd-117">ReleasedVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="a97bd-118">Benachrichtigt den Host, dass die CLR die Verwendung des angegebenen Speichers beendet hat.</span><span class="sxs-lookup"><span data-stu-id="a97bd-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="a97bd-119">VirtualAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="a97bd-120">Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses reserviert oder übergibt.</span><span class="sxs-lookup"><span data-stu-id="a97bd-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="a97bd-121">VirtualFree-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="a97bd-122">Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Bereich von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses freigibt, decommittet oder freigibt bzw. den Seitenbereich debugübergibt.</span><span class="sxs-lookup"><span data-stu-id="a97bd-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="a97bd-123">VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="a97bd-124">Dient als logischer Wrapper für die entsprechende Win32-Funktion, mit der der Schutz für einen Bereich von zugegebenen Seiten im virtuellen Adressraum des aufrufenden Prozesses geändert wird.</span><span class="sxs-lookup"><span data-stu-id="a97bd-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="a97bd-125">VirtualQuery-Methode</span><span class="sxs-lookup"><span data-stu-id="a97bd-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="a97bd-126">Dient als logischer Wrapper für die entsprechende Win32-Funktion, die Informationen zu einem Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abruft.</span><span class="sxs-lookup"><span data-stu-id="a97bd-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a97bd-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a97bd-127">Remarks</span></span>  
 <span data-ttu-id="a97bd-128">`IHostMemoryManager` bietet auch Methoden für die CLR zum Abrufen eines Zeigers, über den Arbeitsspeicher Anforderungen auf dem Heap gesendet werden, und um die Arbeitsspeicher Auslastung des Prozesses zu erhalten, wie vom Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a97bd-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a97bd-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a97bd-129">Requirements</span></span>  
 <span data-ttu-id="a97bd-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a97bd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a97bd-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a97bd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a97bd-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a97bd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a97bd-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a97bd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97bd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a97bd-134">See also</span></span>

- [<span data-ttu-id="a97bd-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a97bd-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="a97bd-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a97bd-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
