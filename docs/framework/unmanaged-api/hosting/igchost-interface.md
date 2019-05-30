---
title: IGCHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 167e2477e5185112408793e145bc5a4fabea7fc8
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377613"
---
# <a name="igchost-interface"></a><span data-ttu-id="acade-102">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acade-102">IGCHost Interface</span></span>
<span data-ttu-id="acade-103">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="acade-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acade-104">Ab .NET Framework 4.5, können Sie die [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) Methode, um die Größe der eine Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 auf Werte größer als festlegen die `DWORD` Grenzwert, der vom auferlegt wird die [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="acade-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acade-105">Diese Schnittstelle ist für die Verwendung durch Experten vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="acade-105">This interface is for expert usage only.</span></span> <span data-ttu-id="acade-106">Sie können die Leistung einer Anwendung beeinträchtigen, wenn nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="acade-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acade-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="acade-107">Methods</span></span>  
  
|<span data-ttu-id="acade-108">Methode</span><span class="sxs-lookup"><span data-stu-id="acade-108">Method</span></span>|<span data-ttu-id="acade-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acade-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acade-110">Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="acade-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="acade-111">Erzwingt, dass eine Collection für die angegebene Generation, unabhängig vom Status des aktuellen Garbagecollection durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="acade-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="acade-112">GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="acade-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="acade-113">Ruft die Statistiken für den aktuellen Zustand des Garbage Collection-Systems ab.</span><span class="sxs-lookup"><span data-stu-id="acade-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="acade-114">GetThreadStats-Methode</span><span class="sxs-lookup"><span data-stu-id="acade-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="acade-115">Ruft die Statistiken pro Thread für die Garbagecollection ab.</span><span class="sxs-lookup"><span data-stu-id="acade-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="acade-116">SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="acade-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="acade-117">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="acade-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="acade-118">SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="acade-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="acade-119">Legt die maximale Größe des virtuellen Arbeitsspeichers von der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="acade-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acade-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acade-120">Requirements</span></span>  
 <span data-ttu-id="acade-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acade-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acade-122">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="acade-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="acade-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="acade-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acade-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acade-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acade-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acade-125">See also</span></span>

- [<span data-ttu-id="acade-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="acade-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="acade-127">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="acade-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
