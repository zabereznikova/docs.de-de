---
title: ICLRGCManager2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4a8b51cf4297c1ccadbef8730c06148263d310e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="3ce3c-102">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ce3c-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="3ce3c-103">Enthält Methoden, die einen Host für die Interaktion mit der common Language Runtime, Garbage Collection-System zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3ce3c-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ce3c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ce3c-104">Methods</span></span>  
  
|<span data-ttu-id="3ce3c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3ce3c-105">Method</span></span>|<span data-ttu-id="3ce3c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ce3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ce3c-107">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="3ce3c-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="3ce3c-108">Legt die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0.</span><span class="sxs-lookup"><span data-stu-id="3ce3c-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="3ce3c-109">Ermöglicht die Generation 0 und größer als Größe der Segmente `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="3ce3c-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ce3c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ce3c-110">Remarks</span></span>  
 <span data-ttu-id="3ce3c-111">Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3ce3c-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="3ce3c-112">Die common Language Runtime (CLR) implementiert, die Garbage Collection-Mechanismus, mit der verwalteten <xref:System.GC> Typ.</span><span class="sxs-lookup"><span data-stu-id="3ce3c-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="3ce3c-113">Weitere Informationen zur Garbage Collection-Systems finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="3ce3c-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ce3c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ce3c-114">Requirements</span></span>  
 <span data-ttu-id="3ce3c-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ce3c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ce3c-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3ce3c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ce3c-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3ce3c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ce3c-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ce3c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce3c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ce3c-119">See Also</span></span>  
 [<span data-ttu-id="3ce3c-120">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="3ce3c-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="3ce3c-121">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="3ce3c-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="3ce3c-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ce3c-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="3ce3c-123">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ce3c-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="3ce3c-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ce3c-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3ce3c-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="3ce3c-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
