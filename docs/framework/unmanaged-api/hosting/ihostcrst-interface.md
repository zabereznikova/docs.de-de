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
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130526"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="5ee9b-102">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ee9b-102">IHostCrst Interface</span></span>
<span data-ttu-id="5ee9b-103">Dient als Host Darstellung eines kritischen Abschnitts zum Threading.</span><span class="sxs-lookup"><span data-stu-id="5ee9b-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ee9b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5ee9b-104">Methods</span></span>  
  
|<span data-ttu-id="5ee9b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5ee9b-105">Method</span></span>|<span data-ttu-id="5ee9b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ee9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ee9b-107">Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee9b-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="5ee9b-108">Wechselt in den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5ee9b-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="5ee9b-109">Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee9b-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="5ee9b-110">Verlässt den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5ee9b-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="5ee9b-111">SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee9b-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="5ee9b-112">Legt die drehanzahl für den kritischen Abschnitt fest.</span><span class="sxs-lookup"><span data-stu-id="5ee9b-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="5ee9b-113">TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee9b-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="5ee9b-114">Versucht, den kritischen Abschnitt einzugeben, und meldet einen Erfolg oder Fehler sofort.</span><span class="sxs-lookup"><span data-stu-id="5ee9b-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ee9b-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ee9b-115">Remarks</span></span>  
 <span data-ttu-id="5ee9b-116">`IHostCrst` ermöglicht es dem Common Language Runtime (CLR), direkt mit der Darstellung eines kritischen Abschnitts des Hosts zu kommunizieren, anstatt Win32-Funktionen wie `EnterCriticalSection` oder `LeaveCriticalSection`zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ee9b-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee9b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ee9b-117">Requirements</span></span>  
 <span data-ttu-id="5ee9b-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee9b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee9b-119">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5ee9b-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ee9b-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5ee9b-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ee9b-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee9b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee9b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ee9b-122">See also</span></span>

- [<span data-ttu-id="5ee9b-123">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ee9b-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5ee9b-124">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ee9b-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="5ee9b-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5ee9b-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
