---
title: IHostMalloc-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc
helpviewer_keywords: IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f788456065a5508441b9fec38ad4a7f531f9f303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="575e9-102">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="575e9-102">IHostMalloc Interface</span></span>
<span data-ttu-id="575e9-103">Enthält Methoden, die die common Language Runtime (CLR) zum Anfordern von differenzierter Zuordnungen aus dem Heap über den Host zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="575e9-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="575e9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="575e9-104">Methods</span></span>  
  
|<span data-ttu-id="575e9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="575e9-105">Method</span></span>|<span data-ttu-id="575e9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="575e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="575e9-107">Alloc-Methode</span><span class="sxs-lookup"><span data-stu-id="575e9-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="575e9-108">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap belegen.</span><span class="sxs-lookup"><span data-stu-id="575e9-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="575e9-109">DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="575e9-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="575e9-110">Fordert an, dass der Host die angeforderte Menge an Arbeitsspeicher aus dem Heap reserviert und außerdem nachverfolgt, in dem der Speicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="575e9-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="575e9-111">Free-Methode</span><span class="sxs-lookup"><span data-stu-id="575e9-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="575e9-112">Speicher, der mit belegt wurde freigegeben wird die `Alloc` Methode.</span><span class="sxs-lookup"><span data-stu-id="575e9-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="575e9-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="575e9-113">Remarks</span></span>  
 <span data-ttu-id="575e9-114">Die CLR ruft einen Schnittstellenzeiger auf eine `IHostMalloc` Instanz durch Aufrufen der [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="575e9-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="575e9-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="575e9-115">Requirements</span></span>  
 <span data-ttu-id="575e9-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="575e9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="575e9-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="575e9-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="575e9-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="575e9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="575e9-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="575e9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575e9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="575e9-120">See Also</span></span>  
 [<span data-ttu-id="575e9-121">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="575e9-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="575e9-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="575e9-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
