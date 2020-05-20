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
ms.openlocfilehash: 0f3ecc0d497eaee937647df47ba0956335a2fe41
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703944"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="5844d-102">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5844d-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="5844d-103">Stellt Methoden bereit, mit denen ein Host mit dem Garbage Collection System des Common Language Runtime interagieren kann.</span><span class="sxs-lookup"><span data-stu-id="5844d-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5844d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5844d-104">Methods</span></span>  
  
|<span data-ttu-id="5844d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5844d-105">Method</span></span>|<span data-ttu-id="5844d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5844d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5844d-107">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="5844d-107">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="5844d-108">Legt die Größe eines Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems fest.</span><span class="sxs-lookup"><span data-stu-id="5844d-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="5844d-109">Aktiviert die Generation 0 und die Segment Größen größer als `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="5844d-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5844d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5844d-110">Remarks</span></span>  
 <span data-ttu-id="5844d-111">Diese Schnittstelle erbt von der [ICLRGCManager-Schnittstelle](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5844d-111">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="5844d-112">Der Common Language Runtime (CLR) implementiert seinen Garbage Collection Mechanismus mit dem verwalteten <xref:System.GC> Typ.</span><span class="sxs-lookup"><span data-stu-id="5844d-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="5844d-113">Weitere Informationen zum Garbage Collection System finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="5844d-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5844d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5844d-114">Requirements</span></span>  
 <span data-ttu-id="5844d-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5844d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5844d-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5844d-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5844d-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5844d-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5844d-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5844d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5844d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5844d-119">See also</span></span>

- [<span data-ttu-id="5844d-120">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="5844d-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="5844d-121">COR_GC_STATS-Struktur</span><span class="sxs-lookup"><span data-stu-id="5844d-121">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="5844d-122">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5844d-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="5844d-123">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5844d-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="5844d-124">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5844d-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5844d-125">Hosting</span><span class="sxs-lookup"><span data-stu-id="5844d-125">Hosting</span></span>](index.md)
