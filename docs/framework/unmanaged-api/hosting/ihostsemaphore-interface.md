---
title: IHostSemaphore-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7d4a295832a958fb6a8fe2e6c43a09135500d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696677"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="44622-102">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44622-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="44622-103">Stellt eine Semaphore für das Threading teilweise Implementierung des Hosts.</span><span class="sxs-lookup"><span data-stu-id="44622-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44622-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="44622-104">Methods</span></span>  
  
|<span data-ttu-id="44622-105">Methode</span><span class="sxs-lookup"><span data-stu-id="44622-105">Method</span></span>|<span data-ttu-id="44622-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44622-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44622-107">ReleaseSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="44622-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="44622-108">Erhöht die Anzahl der aktuellen `IHostSemaphore` Instanz, um den angegebenen Betrag.</span><span class="sxs-lookup"><span data-stu-id="44622-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="44622-109">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="44622-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="44622-110">Bewirkt, dass die aktuelle `IHostSemaphore` Instanz warten, bis sie einen Besitzer hat oder die angegebene Zeitspanne verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="44622-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44622-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44622-111">Requirements</span></span>  
 <span data-ttu-id="44622-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44622-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44622-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="44622-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44622-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="44622-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44622-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44622-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44622-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44622-116">See also</span></span>

- [<span data-ttu-id="44622-117">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44622-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="44622-118">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44622-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="44622-119">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44622-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="44622-120">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44622-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="44622-121">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="44622-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
