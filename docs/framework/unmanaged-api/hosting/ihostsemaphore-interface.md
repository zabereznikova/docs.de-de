---
title: IHostSemaphore-Schnittstelle
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
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bcc6a9a7847932e9e469cdbffc9792e1d5860570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="f6b3b-102">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6b3b-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="f6b3b-103">Stellt eine Semaphore für threading Implementierung des Hosts.</span><span class="sxs-lookup"><span data-stu-id="f6b3b-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6b3b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f6b3b-104">Methods</span></span>  
  
|<span data-ttu-id="f6b3b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f6b3b-105">Method</span></span>|<span data-ttu-id="f6b3b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6b3b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6b3b-107">ReleaseSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="f6b3b-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="f6b3b-108">Erhöht die Anzahl der aktuellen `IHostSemaphore` Instanz, um den angegebenen Betrag.</span><span class="sxs-lookup"><span data-stu-id="f6b3b-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="f6b3b-109">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="f6b3b-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="f6b3b-110">Bewirkt, dass der aktuelle `IHostSemaphore` Instanz warten, bis er Besitzer ist oder die angegebene Zeitspanne verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="f6b3b-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6b3b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6b3b-111">Requirements</span></span>  
 <span data-ttu-id="f6b3b-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6b3b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b3b-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6b3b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6b3b-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f6b3b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6b3b-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b3b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b3b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6b3b-116">See Also</span></span>  
 [<span data-ttu-id="f6b3b-117">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6b3b-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="f6b3b-118">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6b3b-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="f6b3b-119">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6b3b-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="f6b3b-120">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6b3b-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="f6b3b-121">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f6b3b-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
