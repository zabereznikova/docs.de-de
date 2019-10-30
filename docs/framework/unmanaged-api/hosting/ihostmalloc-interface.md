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
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136775"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="2ae49-102">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ae49-102">IHostMalloc Interface</span></span>
<span data-ttu-id="2ae49-103">Stellt Methoden bereit, die es dem Common Language Runtime (CLR) ermöglichen, differenzierte Zuordnungen aus dem Heap über den Host anzufordern.</span><span class="sxs-lookup"><span data-stu-id="2ae49-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ae49-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2ae49-104">Methods</span></span>  
  
|<span data-ttu-id="2ae49-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2ae49-105">Method</span></span>|<span data-ttu-id="2ae49-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ae49-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ae49-107">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="2ae49-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="2ae49-108">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist.</span><span class="sxs-lookup"><span data-stu-id="2ae49-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="2ae49-109">DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="2ae49-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="2ae49-110">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Arbeitsspeicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ae49-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="2ae49-111">Free-Methode</span><span class="sxs-lookup"><span data-stu-id="2ae49-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="2ae49-112">Gibt Arbeitsspeicher frei, der mithilfe der `Alloc`-Methode reserviert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ae49-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ae49-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ae49-113">Remarks</span></span>  
 <span data-ttu-id="2ae49-114">Die CLR ruft durch Aufrufen der [IHostMemoryManager:: createmzuzugsmethode](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) einen Schnittstellen Zeiger auf eine `IHostMalloc` Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="2ae49-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ae49-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ae49-115">Requirements</span></span>  
 <span data-ttu-id="2ae49-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ae49-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ae49-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2ae49-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ae49-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2ae49-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ae49-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ae49-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae49-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ae49-120">See also</span></span>

- [<span data-ttu-id="2ae49-121">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ae49-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="2ae49-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2ae49-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
