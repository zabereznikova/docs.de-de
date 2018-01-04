---
title: IGCHost-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 77a2cab35785aa39571d39bdd369fa26cdbcd1d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="igchost-interface"></a><span data-ttu-id="1241b-102">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1241b-102">IGCHost Interface</span></span>
<span data-ttu-id="1241b-103">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern des einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="1241b-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1241b-104">Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], können Sie die [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) -Methode die Größe der Garbage Collection-Segment und die maximale Größe der Generation 0, die Garbage Collection-System auf Werte größer als der `DWORD` Grenzwert, der vom auferlegt wird die [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="1241b-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1241b-105">Diese Schnittstelle ist für die Verwendung durch Experten nur.</span><span class="sxs-lookup"><span data-stu-id="1241b-105">This interface is for expert usage only.</span></span> <span data-ttu-id="1241b-106">Er kann die Leistung einer Anwendung beeinträchtigen, wenn Sie nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="1241b-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1241b-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="1241b-107">Methods</span></span>  
  
|<span data-ttu-id="1241b-108">Methode</span><span class="sxs-lookup"><span data-stu-id="1241b-108">Method</span></span>|<span data-ttu-id="1241b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1241b-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1241b-110">Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="1241b-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="1241b-111">Erzwingt, dass eine Sammlung aus, für die angegebene Generation, unabhängig vom Zustand der aktuellen Garbagecollection durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1241b-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="1241b-112">GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="1241b-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="1241b-113">Ruft die Statistiken für den aktuellen Zustand des Garbage Collection-Systems an.</span><span class="sxs-lookup"><span data-stu-id="1241b-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="1241b-114">GetThreadStats-Methode</span><span class="sxs-lookup"><span data-stu-id="1241b-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="1241b-115">Ruft die Statistiken pro Thread für die Garbagecollection ab.</span><span class="sxs-lookup"><span data-stu-id="1241b-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="1241b-116">SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="1241b-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="1241b-117">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="1241b-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="1241b-118">SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="1241b-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="1241b-119">Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="1241b-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1241b-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1241b-120">Requirements</span></span>  
 <span data-ttu-id="1241b-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1241b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1241b-122">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="1241b-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="1241b-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1241b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1241b-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1241b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1241b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1241b-125">See Also</span></span>  
 [<span data-ttu-id="1241b-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1241b-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="1241b-127">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="1241b-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
