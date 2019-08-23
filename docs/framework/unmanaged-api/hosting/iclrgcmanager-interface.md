---
title: ICLRGCManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76d1071ddde1509f16fd786afa4c05c05224d051
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966211"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="a3f8c-102">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3f8c-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="a3f8c-103">Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="a3f8c-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3f8c-104">Beginnend mit dem .NET Framework 4,5 können Sie die [ICLRGCManager2:: setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode verwenden, um die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festzulegen, die größer als die `DWORD`Limit, das von der [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) -Methode vorgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a3f8c-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3f8c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a3f8c-105">Methods</span></span>  
  
|<span data-ttu-id="a3f8c-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a3f8c-106">Method</span></span>|<span data-ttu-id="a3f8c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3f8c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3f8c-108">Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="a3f8c-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="a3f8c-109">Erzwingt eine Garbage Collection für die angegebene Generierung.</span><span class="sxs-lookup"><span data-stu-id="a3f8c-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="a3f8c-110">GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="a3f8c-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="a3f8c-111">Ruft einen Satz aktueller Statistiken zum Garbage Collection System ab.</span><span class="sxs-lookup"><span data-stu-id="a3f8c-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="a3f8c-112">SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="a3f8c-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="a3f8c-113">Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.</span><span class="sxs-lookup"><span data-stu-id="a3f8c-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f8c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3f8c-114">Remarks</span></span>  
 <span data-ttu-id="a3f8c-115">Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ.</span><span class="sxs-lookup"><span data-stu-id="a3f8c-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="a3f8c-116">Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="a3f8c-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f8c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3f8c-117">Requirements</span></span>  
 <span data-ttu-id="a3f8c-118">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f8c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f8c-119">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a3f8c-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3f8c-120">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a3f8c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f8c-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f8c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f8c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3f8c-122">See also</span></span>

- [<span data-ttu-id="a3f8c-123">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="a3f8c-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="a3f8c-124">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="a3f8c-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="a3f8c-125">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3f8c-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a3f8c-126">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a3f8c-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="a3f8c-127">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a3f8c-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a3f8c-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="a3f8c-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
