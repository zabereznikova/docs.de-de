---
title: IHostCrst-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 350af708456914c73929d2b8887173cf784d4294
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680556"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="5f63c-102">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f63c-102">IHostCrst Interface</span></span>

<span data-ttu-id="5f63c-103">Dient als Host Darstellung eines kritischen Abschnitts zum Threading.</span><span class="sxs-lookup"><span data-stu-id="5f63c-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f63c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5f63c-104">Methods</span></span>  
  
|<span data-ttu-id="5f63c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5f63c-105">Method</span></span>|<span data-ttu-id="5f63c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5f63c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f63c-107">Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="5f63c-107">Enter Method</span></span>](ihostcrst-enter-method.md)|<span data-ttu-id="5f63c-108">Wechselt in den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5f63c-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="5f63c-109">Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="5f63c-109">Leave Method</span></span>](ihostcrst-leave-method.md)|<span data-ttu-id="5f63c-110">Verlässt den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5f63c-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="5f63c-111">SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5f63c-111">SetSpinCount Method</span></span>](ihostcrst-setspincount-method.md)|<span data-ttu-id="5f63c-112">Legt die drehanzahl für den kritischen Abschnitt fest.</span><span class="sxs-lookup"><span data-stu-id="5f63c-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="5f63c-113">TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="5f63c-113">TryEnter Method</span></span>](ihostcrst-tryenter-method.md)|<span data-ttu-id="5f63c-114">Versucht, den kritischen Abschnitt einzugeben, und meldet einen Erfolg oder Fehler sofort.</span><span class="sxs-lookup"><span data-stu-id="5f63c-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f63c-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f63c-115">Remarks</span></span>  

 <span data-ttu-id="5f63c-116">`IHostCrst` ermöglicht dem Common Language Runtime (CLR), direkt mit der Darstellung eines kritischen Abschnitts des Hosts zu kommunizieren, anstatt Win32-Funktionen wie oder zu `EnterCriticalSection` verwenden `LeaveCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="5f63c-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f63c-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5f63c-117">Requirements</span></span>  

 <span data-ttu-id="5f63c-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f63c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f63c-119">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5f63c-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f63c-120">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5f63c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f63c-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f63c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f63c-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f63c-122">See also</span></span>

- [<span data-ttu-id="5f63c-123">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f63c-123">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="5f63c-124">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f63c-124">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="5f63c-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5f63c-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
