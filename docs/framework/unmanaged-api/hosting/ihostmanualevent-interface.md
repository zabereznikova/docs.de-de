---
title: IHostManualEvent-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136782"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="a7638-102">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7638-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="a7638-103">Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="a7638-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7638-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a7638-104">Methods</span></span>  
  
|<span data-ttu-id="a7638-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a7638-105">Method</span></span>|<span data-ttu-id="a7638-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7638-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7638-107">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="a7638-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="a7638-108">Setzt die aktuelle `IHostManualEvent`-Instanz auf einen nicht signalisierten Zustand zurück.</span><span class="sxs-lookup"><span data-stu-id="a7638-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="a7638-109">Set-Methode</span><span class="sxs-lookup"><span data-stu-id="a7638-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="a7638-110">Legt die aktuelle `IHostManualEvent` Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="a7638-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="a7638-111">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="a7638-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="a7638-112">Bewirkt, dass die aktuelle `IHostManualEvent` Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.</span><span class="sxs-lookup"><span data-stu-id="a7638-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7638-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7638-113">Requirements</span></span>  
 <span data-ttu-id="a7638-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7638-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7638-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a7638-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7638-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a7638-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7638-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7638-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7638-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7638-118">See also</span></span>

- [<span data-ttu-id="a7638-119">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7638-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a7638-120">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7638-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="a7638-121">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7638-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="a7638-122">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7638-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="a7638-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a7638-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
