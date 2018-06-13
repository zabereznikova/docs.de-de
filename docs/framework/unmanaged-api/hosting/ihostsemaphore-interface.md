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
ms.openlocfilehash: 103deb5ec46ba8c1d385c5339bc52a0c220c4c93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439767"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="798a5-102">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798a5-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="798a5-103">Stellt eine Semaphore für threading Implementierung des Hosts.</span><span class="sxs-lookup"><span data-stu-id="798a5-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="798a5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="798a5-104">Methods</span></span>  
  
|<span data-ttu-id="798a5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="798a5-105">Method</span></span>|<span data-ttu-id="798a5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="798a5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="798a5-107">ReleaseSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="798a5-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="798a5-108">Erhöht die Anzahl der aktuellen `IHostSemaphore` Instanz, um den angegebenen Betrag.</span><span class="sxs-lookup"><span data-stu-id="798a5-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="798a5-109">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="798a5-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="798a5-110">Bewirkt, dass der aktuelle `IHostSemaphore` Instanz warten, bis er Besitzer ist oder die angegebene Zeitspanne verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="798a5-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="798a5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="798a5-111">Requirements</span></span>  
 <span data-ttu-id="798a5-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="798a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="798a5-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="798a5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="798a5-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="798a5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="798a5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="798a5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="798a5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="798a5-116">See Also</span></span>  
 [<span data-ttu-id="798a5-117">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798a5-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="798a5-118">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798a5-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="798a5-119">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798a5-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="798a5-120">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="798a5-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="798a5-121">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="798a5-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
