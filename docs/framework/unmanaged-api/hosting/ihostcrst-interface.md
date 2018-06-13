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
ms.openlocfilehash: 88f2ef8299911905d651ad5c3076dc9c74f397f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438918"
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="14577-102">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14577-102">IHostCrst Interface</span></span>
<span data-ttu-id="14577-103">Dient als Host Darstellung eines kritischen Abschnitts für threading.</span><span class="sxs-lookup"><span data-stu-id="14577-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14577-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="14577-104">Methods</span></span>  
  
|<span data-ttu-id="14577-105">Methode</span><span class="sxs-lookup"><span data-stu-id="14577-105">Method</span></span>|<span data-ttu-id="14577-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14577-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14577-107">Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="14577-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="14577-108">Wechselt in den kritischen Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="14577-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="14577-109">Leave-Methode</span><span class="sxs-lookup"><span data-stu-id="14577-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="14577-110">Verlässt die kritischen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="14577-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="14577-111">SetSpinCount-Methode</span><span class="sxs-lookup"><span data-stu-id="14577-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="14577-112">Legt die Anzahl der Drehfeld für die kritischen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="14577-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="14577-113">TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="14577-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="14577-114">Versucht, den kritischen Abschnitt und berichtet über Erfolg oder Fehler sofort eingeben.</span><span class="sxs-lookup"><span data-stu-id="14577-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14577-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14577-115">Remarks</span></span>  
 <span data-ttu-id="14577-116">`IHostCrst` ermöglicht die common Language Runtime (CLR) die direkte Kommunikation mit dem Host-Darstellung eines kritischen Abschnitts, anstatt Win32-Funktionen wie z. B. `EnterCriticalSection` oder `LeaveCriticalSection`.</span><span class="sxs-lookup"><span data-stu-id="14577-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14577-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14577-117">Requirements</span></span>  
 <span data-ttu-id="14577-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14577-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14577-119">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14577-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14577-120">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="14577-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14577-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14577-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14577-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14577-122">See Also</span></span>  
 [<span data-ttu-id="14577-123">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14577-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="14577-124">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14577-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="14577-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="14577-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
