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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb09422872a0d9565be286c25ca1b28d1c45e08f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501697"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="91097-102">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91097-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="91097-103">Stellt eine Darstellung der ein Ereignis mit manueller Rücksetzung Implementierung des Hosts.</span><span class="sxs-lookup"><span data-stu-id="91097-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91097-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="91097-104">Methods</span></span>  
  
|<span data-ttu-id="91097-105">Methode</span><span class="sxs-lookup"><span data-stu-id="91097-105">Method</span></span>|<span data-ttu-id="91097-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91097-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91097-107">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="91097-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="91097-108">Setzt die aktuelle `IHostManualEvent` Instanz in einen nicht signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="91097-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="91097-109">Set-Methode</span><span class="sxs-lookup"><span data-stu-id="91097-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="91097-110">Legt die aktuelle `IHostManualEvent` Instanz in einem signalisierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="91097-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="91097-111">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="91097-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="91097-112">Bewirkt, dass die aktuelle `IHostManualEvent` Instanz warten, bis sie gehört, oder einen bestimmten Zeitraum abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="91097-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91097-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91097-113">Requirements</span></span>  
 <span data-ttu-id="91097-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91097-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91097-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91097-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91097-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="91097-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91097-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91097-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91097-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91097-118">See also</span></span>
- [<span data-ttu-id="91097-119">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91097-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="91097-120">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91097-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="91097-121">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91097-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="91097-122">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91097-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="91097-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91097-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
