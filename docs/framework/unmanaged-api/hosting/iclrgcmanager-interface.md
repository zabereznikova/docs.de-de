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
ms.openlocfilehash: 76a50be6da790ed7bd193c489d36e2823cdbe587
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616960"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="8e7be-102">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e7be-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="8e7be-103">Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="8e7be-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e7be-104">Beginnend mit dem .NET Framework 4,5 können Sie die [ICLRGCManager2:: setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode verwenden, um die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festzulegen, die den `DWORD` von der [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) -Methode festgelegten Grenzwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="8e7be-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e7be-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8e7be-105">Methods</span></span>  
  
|<span data-ttu-id="8e7be-106">Methode</span><span class="sxs-lookup"><span data-stu-id="8e7be-106">Method</span></span>|<span data-ttu-id="8e7be-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8e7be-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e7be-108">Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="8e7be-108">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="8e7be-109">Erzwingt eine Garbage Collection für die angegebene Generierung.</span><span class="sxs-lookup"><span data-stu-id="8e7be-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="8e7be-110">GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="8e7be-110">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="8e7be-111">Ruft einen Satz aktueller Statistiken zum Garbage Collection System ab.</span><span class="sxs-lookup"><span data-stu-id="8e7be-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="8e7be-112">SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="8e7be-112">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="8e7be-113">Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.</span><span class="sxs-lookup"><span data-stu-id="8e7be-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e7be-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e7be-114">Remarks</span></span>  
 <span data-ttu-id="8e7be-115">Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ.</span><span class="sxs-lookup"><span data-stu-id="8e7be-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="8e7be-116">Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="8e7be-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e7be-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e7be-117">Requirements</span></span>  
 <span data-ttu-id="8e7be-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e7be-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e7be-119">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8e7be-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e7be-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8e7be-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e7be-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e7be-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e7be-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e7be-122">See also</span></span>

- [<span data-ttu-id="8e7be-123">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="8e7be-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="8e7be-124">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="8e7be-124">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="8e7be-125">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e7be-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8e7be-126">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8e7be-126">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="8e7be-127">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8e7be-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8e7be-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="8e7be-128">Hosting</span></span>](index.md)
