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
ms.openlocfilehash: 9d6c9d22f4e50c21e2f41b7efd402907ff5843db
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805215"
---
# <a name="igchost-interface"></a><span data-ttu-id="4f942-102">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f942-102">IGCHost Interface</span></span>
<span data-ttu-id="4f942-103">Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f942-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f942-104">Beginnend mit dem .NET Framework 4,5 können Sie die [IGCHost2:: setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) -Methode verwenden, um die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festzulegen, die den `DWORD` von der [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) -Methode festgelegten Grenzwert überschreiten.</span><span class="sxs-lookup"><span data-stu-id="4f942-104">Starting with the .NET Framework 4.5, you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f942-105">Diese Schnittstelle ist nur für die Verwendung durch Experten vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4f942-105">This interface is for expert usage only.</span></span> <span data-ttu-id="4f942-106">Dies kann die Leistung einer Anwendung beeinträchtigen, wenn Sie nicht ordnungsgemäß verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f942-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f942-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="4f942-107">Methods</span></span>  
  
|<span data-ttu-id="4f942-108">Methode</span><span class="sxs-lookup"><span data-stu-id="4f942-108">Method</span></span>|<span data-ttu-id="4f942-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4f942-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f942-110">Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="4f942-110">Collect Method</span></span>](igchost-collect-method.md)|<span data-ttu-id="4f942-111">Erzwingt, dass eine Auflistung für die angegebene Generierung stattfindet, unabhängig vom Zustand des aktuellen Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="4f942-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="4f942-112">GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="4f942-112">GetStats Method</span></span>](igchost-getstats-method.md)|<span data-ttu-id="4f942-113">Ruft die Statistiken für den aktuellen Status des Garbage Collection Systems ab.</span><span class="sxs-lookup"><span data-stu-id="4f942-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="4f942-114">GetThreadStats-Methode</span><span class="sxs-lookup"><span data-stu-id="4f942-114">GetThreadStats Method</span></span>](igchost-getthreadstats-method.md)|<span data-ttu-id="4f942-115">Ruft die Statistiken pro Thread für Garbage Collection ab.</span><span class="sxs-lookup"><span data-stu-id="4f942-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="4f942-116">SetGCStartupLimits-Methode</span><span class="sxs-lookup"><span data-stu-id="4f942-116">SetGCStartupLimits Method</span></span>](igchost-setgcstartuplimits-method.md)|<span data-ttu-id="4f942-117">Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="4f942-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="4f942-118">SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="4f942-118">SetVirtualMemLimit Method</span></span>](igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="4f942-119">Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="4f942-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f942-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f942-120">Requirements</span></span>  
 <span data-ttu-id="4f942-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f942-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f942-122">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="4f942-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4f942-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4f942-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f942-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f942-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f942-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f942-125">See also</span></span>

- [<span data-ttu-id="4f942-126">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4f942-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4f942-127">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="4f942-127">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
