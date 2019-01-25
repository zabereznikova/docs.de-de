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
ms.openlocfilehash: 9897526882a8ae53410a7744f78c558dfa6981e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708583"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="55265-102">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55265-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="55265-103">Enthält Methoden, die einen Host für die Interaktion mit der common Language Runtime, Garbage Collection-System zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="55265-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55265-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="55265-104">Methods</span></span>  
  
|<span data-ttu-id="55265-105">Methode</span><span class="sxs-lookup"><span data-stu-id="55265-105">Method</span></span>|<span data-ttu-id="55265-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55265-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55265-107">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="55265-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="55265-108">Legt die Größe der eine Garbage Collection-Segment und die maximale Größe der Garbage Collection-Systems die Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="55265-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="55265-109">Ermöglicht die Generation 0 und größer als Größe der Segmente `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="55265-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55265-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55265-110">Remarks</span></span>  
 <span data-ttu-id="55265-111">Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="55265-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="55265-112">Die common Language Runtime (CLR) implementiert, die Garbage Collection-Mechanismus, mit der verwalteten <xref:System.GC> Typ.</span><span class="sxs-lookup"><span data-stu-id="55265-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="55265-113">Weitere Informationen zur Garbage Collection-Systems finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="55265-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55265-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55265-114">Requirements</span></span>  
 <span data-ttu-id="55265-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55265-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55265-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55265-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55265-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="55265-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55265-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55265-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55265-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55265-119">See also</span></span>
- [<span data-ttu-id="55265-120">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="55265-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="55265-121">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="55265-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="55265-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55265-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="55265-123">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="55265-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="55265-124">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="55265-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="55265-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="55265-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
