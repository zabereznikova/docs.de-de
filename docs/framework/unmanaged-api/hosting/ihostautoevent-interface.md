---
title: IHostAutoEvent-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7f2b65f263256fe887c61c7b866beaa0038c37d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437413"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="1a617-102">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a617-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="1a617-103">Bietet eine Darstellung der Implementierung des Hosts ein AutoReset-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="1a617-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1a617-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1a617-104">Methods</span></span>  
  
|<span data-ttu-id="1a617-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1a617-105">Method</span></span>|<span data-ttu-id="1a617-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a617-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1a617-107">Set-Methode</span><span class="sxs-lookup"><span data-stu-id="1a617-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="1a617-108">Legt das aktuelle `IHostAutoEvent` Instanz zum Zustand "signalisiert".</span><span class="sxs-lookup"><span data-stu-id="1a617-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="1a617-109">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="1a617-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="1a617-110">Bewirkt, dass der aktuelle `IHostAutoEvent` Instanz warten, bis das Ereignis der Besitzer ist oder einen bestimmten Zeitraum verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="1a617-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a617-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a617-111">Requirements</span></span>  
 <span data-ttu-id="1a617-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a617-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a617-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1a617-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a617-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1a617-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a617-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a617-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a617-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a617-116">See Also</span></span>  
 [<span data-ttu-id="1a617-117">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a617-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1a617-118">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a617-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="1a617-119">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a617-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="1a617-120">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1a617-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
