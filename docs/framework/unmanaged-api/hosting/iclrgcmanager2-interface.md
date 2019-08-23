---
title: ICLRGCManager2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c54707d4c767fbb644ed892767be8351d2fd95b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966190"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="f60af-102">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f60af-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="f60af-103">Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="f60af-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f60af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f60af-104">Methods</span></span>  
  
|<span data-ttu-id="f60af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f60af-105">Method</span></span>|<span data-ttu-id="f60af-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f60af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f60af-107">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="f60af-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="f60af-108">Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.</span><span class="sxs-lookup"><span data-stu-id="f60af-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="f60af-109">Aktiviert die Generation 0 und die Segment `DWORD`Größen größer als.</span><span class="sxs-lookup"><span data-stu-id="f60af-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f60af-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f60af-110">Remarks</span></span>  
 <span data-ttu-id="f60af-111">Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f60af-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="f60af-112">Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ.</span><span class="sxs-lookup"><span data-stu-id="f60af-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="f60af-113">Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="f60af-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f60af-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f60af-114">Requirements</span></span>  
 <span data-ttu-id="f60af-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f60af-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60af-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f60af-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f60af-117">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f60af-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f60af-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60af-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60af-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f60af-119">See also</span></span>

- [<span data-ttu-id="f60af-120">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="f60af-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="f60af-121">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="f60af-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="f60af-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f60af-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f60af-123">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f60af-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="f60af-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f60af-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f60af-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="f60af-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
