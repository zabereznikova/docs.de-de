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
ms.openlocfilehash: 0f71e4c45e43c2027b12998532f2b04401a51951
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731331"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="137f7-102">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137f7-102">IHostMemoryManager Interface</span></span>

<span data-ttu-id="137f7-103">Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, virtuelle Speicheranforderungen über den Host zu erstellen, statt die standardmäßigen Win32-Funktionen für den virtuellen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="137f7-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="137f7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="137f7-104">Methods</span></span>  
  
|<span data-ttu-id="137f7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-105">Method</span></span>|<span data-ttu-id="137f7-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="137f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="137f7-107">AcquiredVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-107">AcquiredVirtualAddressSpace Method</span></span>](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="137f7-108">Benachrichtigt den Host, dass die Common Language Runtime (CLR) den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="137f7-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="137f7-109">CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-109">CreateMAlloc Method</span></span>](ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="137f7-110">Ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](ihostmalloc-interface.md) -Instanz ab, die verwendet wird, um Speicher Belegungen von einem Heap anzufordern, der vom Host erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="137f7-110">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="137f7-111">GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-111">GetMemoryLoad Method</span></span>](ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="137f7-112">Ruft die Menge an physischem Arbeitsspeicher ab, die derzeit verwendet wird, wie vom Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="137f7-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="137f7-113">NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-113">NeedsVirtualAddressSpace Method</span></span>](ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="137f7-114">Benachrichtigt den Host, dass die CLR versucht, den angegebenen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="137f7-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="137f7-115">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-115">RegisterMemoryNotificationCallback Method</span></span>](ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="137f7-116">Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die CLR über die aktuelle Arbeitsspeicher Auslastung auf dem Computer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="137f7-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="137f7-117">ReleasedVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-117">ReleasedVirtualAddressSpace Method</span></span>](ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="137f7-118">Benachrichtigt den Host, dass die CLR die Verwendung des angegebenen Speichers beendet hat.</span><span class="sxs-lookup"><span data-stu-id="137f7-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="137f7-119">VirtualAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-119">VirtualAlloc Method</span></span>](ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="137f7-120">Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Seitenbereich im virtuellen Adressraum des aufrufenden Prozesses reserviert oder übergibt.</span><span class="sxs-lookup"><span data-stu-id="137f7-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="137f7-121">VirtualFree-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-121">VirtualFree Method</span></span>](ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="137f7-122">Dient als logischer Wrapper für die entsprechende Win32-Funktion, die einen Bereich von Seiten innerhalb des virtuellen Adressraums des aufrufenden Prozesses freigibt, decommittet oder freigibt bzw. den Seitenbereich debugübergibt.</span><span class="sxs-lookup"><span data-stu-id="137f7-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="137f7-123">VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-123">VirtualProtect Method</span></span>](ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="137f7-124">Dient als logischer Wrapper für die entsprechende Win32-Funktion, mit der der Schutz für einen Bereich von zugegebenen Seiten im virtuellen Adressraum des aufrufenden Prozesses geändert wird.</span><span class="sxs-lookup"><span data-stu-id="137f7-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="137f7-125">VirtualQuery-Methode</span><span class="sxs-lookup"><span data-stu-id="137f7-125">VirtualQuery Method</span></span>](ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="137f7-126">Dient als logischer Wrapper für die entsprechende Win32-Funktion, die Informationen zu einem Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses abruft.</span><span class="sxs-lookup"><span data-stu-id="137f7-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="137f7-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="137f7-127">Remarks</span></span>  

 <span data-ttu-id="137f7-128">`IHostMemoryManager` stellt außerdem Methoden bereit, mit denen die CLR einen Zeiger abrufen kann, über den Arbeitsspeicher Anforderungen für den Heap und die Arbeitsspeicher Auslastung im Prozess, wie vom Host gemeldet, abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="137f7-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="137f7-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="137f7-129">Requirements</span></span>  

 <span data-ttu-id="137f7-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="137f7-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="137f7-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="137f7-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="137f7-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="137f7-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="137f7-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="137f7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="137f7-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="137f7-134">See also</span></span>

- [<span data-ttu-id="137f7-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="137f7-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="137f7-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="137f7-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
