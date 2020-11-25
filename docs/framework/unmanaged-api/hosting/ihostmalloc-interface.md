---
title: IHostMalloc-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: 2530c7fcd63f81b566d6623a533bd8e2af084047
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702159"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="e8b35-102">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8b35-102">IHostMalloc Interface</span></span>

<span data-ttu-id="e8b35-103">Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, differenzierte Zuordnungen aus dem Heap über den Host anzufordern.</span><span class="sxs-lookup"><span data-stu-id="e8b35-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8b35-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e8b35-104">Methods</span></span>  
  
|<span data-ttu-id="e8b35-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e8b35-105">Method</span></span>|<span data-ttu-id="e8b35-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e8b35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8b35-107">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="e8b35-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="e8b35-108">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist.</span><span class="sxs-lookup"><span data-stu-id="e8b35-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="e8b35-109">DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="e8b35-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="e8b35-110">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Arbeitsspeicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8b35-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="e8b35-111">Free-Methode</span><span class="sxs-lookup"><span data-stu-id="e8b35-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="e8b35-112">Gibt Arbeitsspeicher frei, der mithilfe der-Methode zugeordnet wurde `Alloc` .</span><span class="sxs-lookup"><span data-stu-id="e8b35-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8b35-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8b35-113">Remarks</span></span>  

 <span data-ttu-id="e8b35-114">Die CLR ruft einen Schnittstellen Zeiger auf eine-Instanz ab, `IHostMalloc` indem die [IHostMemoryManager:: createmzuzugsmethode](ihostmemorymanager-createmalloc-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e8b35-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8b35-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e8b35-115">Requirements</span></span>  

 <span data-ttu-id="e8b35-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8b35-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8b35-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e8b35-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8b35-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8b35-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8b35-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b35-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b35-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8b35-120">See also</span></span>

- [<span data-ttu-id="e8b35-121">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8b35-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="e8b35-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e8b35-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
