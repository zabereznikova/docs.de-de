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
ms.openlocfilehash: 939f100e8ee386642a29c33827a8339caf0467b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193186"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="5b296-102">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b296-102">IHostCrst Interface</span></span>
<span data-ttu-id="5b296-103">Dient als Darstellung des Hosts in einem kritischen Abschnitt für das Threading teilweise.</span><span class="sxs-lookup"><span data-stu-id="5b296-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b296-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5b296-104">Methods</span></span>  
  
|<span data-ttu-id="5b296-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5b296-105">Method</span></span>|<span data-ttu-id="5b296-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b296-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b296-107">Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="5b296-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="5b296-108">Gibt den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5b296-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="5b296-109">Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="5b296-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="5b296-110">Lässt den kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="5b296-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="5b296-111">SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5b296-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="5b296-112">Legt die Spin-Anzahl für den kritischen Abschnitt fest.</span><span class="sxs-lookup"><span data-stu-id="5b296-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="5b296-113">TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="5b296-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="5b296-114">Versucht, den kritischen Abschnitt und Berichte erfolgreich oder fehlerhaft direkt eingeben.</span><span class="sxs-lookup"><span data-stu-id="5b296-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b296-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b296-115">Remarks</span></span>  
 <span data-ttu-id="5b296-116">`IHostCrst` bietet die common Language Runtime (CLR), um direkt mit der Darstellung eines kritischen Abschnitts, die Hosts kommunizieren mithilfe von Win32-Funktionen wie z. B. `EnterCriticalSection` oder `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="5b296-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b296-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b296-117">Requirements</span></span>  
 <span data-ttu-id="5b296-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b296-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b296-119">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b296-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b296-120">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5b296-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b296-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b296-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b296-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b296-122">See also</span></span>

- [<span data-ttu-id="5b296-123">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b296-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5b296-124">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b296-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="5b296-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5b296-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
