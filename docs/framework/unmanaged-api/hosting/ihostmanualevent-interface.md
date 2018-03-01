---
title: IHostManualEvent-Schnittstelle
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0d55500efbe808b2fce16e869422e727b8ed0b93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="acf24-102">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acf24-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="acf24-103">Stellt den Host-Implementierung der eine Repräsentation ein Ereignis für manuelles Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="acf24-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acf24-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="acf24-104">Methods</span></span>  
  
|<span data-ttu-id="acf24-105">Methode</span><span class="sxs-lookup"><span data-stu-id="acf24-105">Method</span></span>|<span data-ttu-id="acf24-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acf24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acf24-107">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="acf24-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="acf24-108">Setzt die aktuelle `IHostManualEvent` Instanz in einen nicht signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="acf24-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="acf24-109">Set-Methode</span><span class="sxs-lookup"><span data-stu-id="acf24-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="acf24-110">Legt das aktuelle `IHostManualEvent` Instanz zum Zustand "signalisiert".</span><span class="sxs-lookup"><span data-stu-id="acf24-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="acf24-111">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="acf24-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="acf24-112">Bewirkt, dass der aktuelle `IHostManualEvent` Instanz warten, bis er Besitzer ist oder einen bestimmten Zeitraum verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="acf24-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acf24-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acf24-113">Requirements</span></span>  
 <span data-ttu-id="acf24-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf24-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf24-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="acf24-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acf24-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="acf24-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acf24-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf24-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf24-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acf24-118">See Also</span></span>  
 [<span data-ttu-id="acf24-119">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acf24-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="acf24-120">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acf24-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="acf24-121">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acf24-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="acf24-122">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acf24-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="acf24-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="acf24-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
