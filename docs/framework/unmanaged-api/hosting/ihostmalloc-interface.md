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
ms.openlocfilehash: 8f4e1cd7586df7d8e2a577d26f06eaed6b2c8bb7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804600"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="1202c-102">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1202c-102">IHostMalloc Interface</span></span>
<span data-ttu-id="1202c-103">Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, differenzierte Zuordnungen aus dem Heap über den Host anzufordern.</span><span class="sxs-lookup"><span data-stu-id="1202c-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1202c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1202c-104">Methods</span></span>  
  
|<span data-ttu-id="1202c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1202c-105">Method</span></span>|<span data-ttu-id="1202c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1202c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1202c-107">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="1202c-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="1202c-108">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist.</span><span class="sxs-lookup"><span data-stu-id="1202c-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="1202c-109">DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="1202c-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="1202c-110">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Arbeitsspeicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="1202c-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="1202c-111">Free-Methode</span><span class="sxs-lookup"><span data-stu-id="1202c-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="1202c-112">Gibt Arbeitsspeicher frei, der mithilfe der-Methode zugeordnet wurde `Alloc` .</span><span class="sxs-lookup"><span data-stu-id="1202c-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1202c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1202c-113">Remarks</span></span>  
 <span data-ttu-id="1202c-114">Die CLR ruft einen Schnittstellen Zeiger auf eine-Instanz ab, `IHostMalloc` indem die [IHostMemoryManager:: createmzuzugsmethode](ihostmemorymanager-createmalloc-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1202c-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1202c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1202c-115">Requirements</span></span>  
 <span data-ttu-id="1202c-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1202c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1202c-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1202c-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1202c-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1202c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1202c-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1202c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1202c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1202c-120">See also</span></span>

- [<span data-ttu-id="1202c-121">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1202c-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="1202c-122">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1202c-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
