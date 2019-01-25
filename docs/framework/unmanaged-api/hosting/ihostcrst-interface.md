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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34a911668db09b255282833cec3e6272b315373b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618658"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="6e4e0-102">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e4e0-102">IHostCrst Interface</span></span>
<span data-ttu-id="6e4e0-103">Dient als Darstellung des Hosts in einem kritischen Abschnitt für das Threading teilweise.</span><span class="sxs-lookup"><span data-stu-id="6e4e0-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e4e0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6e4e0-104">Methods</span></span>  
  
|<span data-ttu-id="6e4e0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6e4e0-105">Method</span></span>|<span data-ttu-id="6e4e0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e4e0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e4e0-107">Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="6e4e0-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="6e4e0-108">Gibt den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="6e4e0-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="6e4e0-109">Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="6e4e0-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="6e4e0-110">Lässt den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="6e4e0-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="6e4e0-111">SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="6e4e0-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="6e4e0-112">Legt die Spin-Anzahl für den kritischen Abschnitt fest.</span><span class="sxs-lookup"><span data-stu-id="6e4e0-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="6e4e0-113">TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="6e4e0-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="6e4e0-114">Versucht, den kritischen Abschnitt und Berichte erfolgreich oder fehlerhaft direkt eingeben.</span><span class="sxs-lookup"><span data-stu-id="6e4e0-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e4e0-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e4e0-115">Remarks</span></span>  
 <span data-ttu-id="6e4e0-116">`IHostCrst` bietet die common Language Runtime (CLR), um direkt mit der Darstellung eines kritischen Abschnitts, die Hosts kommunizieren mithilfe von Win32-Funktionen wie z. B. `EnterCriticalSection` oder `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="6e4e0-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e4e0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e4e0-117">Requirements</span></span>  
 <span data-ttu-id="6e4e0-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e4e0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e4e0-119">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6e4e0-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e4e0-120">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6e4e0-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e4e0-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e4e0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4e0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e4e0-122">See also</span></span>
- [<span data-ttu-id="6e4e0-123">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e4e0-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6e4e0-124">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e4e0-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="6e4e0-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6e4e0-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
