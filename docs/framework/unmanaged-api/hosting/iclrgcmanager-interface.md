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
ms.openlocfilehash: 045b924033630ea98d5a532a62f1037a5972df90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433923"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="fa486-102">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa486-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="fa486-103">Enthält Methoden, die einen Host für die Interaktion mit der common Language Runtime, Garbage Collection-System zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fa486-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa486-104">Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], können Sie die [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) Methode, um die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0 Werte größer festgelegt als die `DWORD` Grenzwert, der vom auferlegt wird die [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="fa486-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa486-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fa486-105">Methods</span></span>  
  
|<span data-ttu-id="fa486-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fa486-106">Method</span></span>|<span data-ttu-id="fa486-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa486-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa486-108">Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="fa486-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="fa486-109">Erzwingt eine Garbagecollection für die angegebene Generation.</span><span class="sxs-lookup"><span data-stu-id="fa486-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="fa486-110">GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="fa486-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="fa486-111">Ruft die aktuellen Statistiken über Garbage Collection-Systems ab.</span><span class="sxs-lookup"><span data-stu-id="fa486-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="fa486-112">SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="fa486-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="fa486-113">Legt die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0.</span><span class="sxs-lookup"><span data-stu-id="fa486-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa486-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa486-114">Remarks</span></span>  
 <span data-ttu-id="fa486-115">Die common Language Runtime (CLR) implementiert, die Garbage Collection-Mechanismus, mit der verwalteten <xref:System.GC> Typ.</span><span class="sxs-lookup"><span data-stu-id="fa486-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="fa486-116">Weitere Informationen zur Garbage Collection-Systems finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="fa486-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa486-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa486-117">Requirements</span></span>  
 <span data-ttu-id="fa486-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa486-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa486-119">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fa486-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa486-120">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fa486-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa486-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa486-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa486-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa486-122">See Also</span></span>  
 [<span data-ttu-id="fa486-123">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="fa486-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="fa486-124">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="fa486-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="fa486-125">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa486-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="fa486-126">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fa486-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="fa486-127">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fa486-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="fa486-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="fa486-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
