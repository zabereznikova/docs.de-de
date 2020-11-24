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
ms.openlocfilehash: 50e37b770e3ee6e0a5cdfca61fc5b09749e5735f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673198"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="cb425-102">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb425-102">IHostManualEvent Interface</span></span>

<span data-ttu-id="cb425-103">Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="cb425-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb425-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cb425-104">Methods</span></span>  
  
|<span data-ttu-id="cb425-105">Methode</span><span class="sxs-lookup"><span data-stu-id="cb425-105">Method</span></span>|<span data-ttu-id="cb425-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cb425-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb425-107">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="cb425-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="cb425-108">Setzt die aktuelle `IHostManualEvent` Instanz auf einen nicht signalisierten Zustand zurück.</span><span class="sxs-lookup"><span data-stu-id="cb425-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="cb425-109">Set-Methode</span><span class="sxs-lookup"><span data-stu-id="cb425-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="cb425-110">Legt die aktuelle `IHostManualEvent` Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="cb425-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="cb425-111">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="cb425-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="cb425-112">Bewirkt, dass die aktuelle `IHostManualEvent` Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.</span><span class="sxs-lookup"><span data-stu-id="cb425-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb425-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cb425-113">Requirements</span></span>  

 <span data-ttu-id="cb425-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb425-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb425-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cb425-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb425-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cb425-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb425-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb425-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb425-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb425-118">See also</span></span>

- [<span data-ttu-id="cb425-119">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb425-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="cb425-120">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb425-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="cb425-121">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb425-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="cb425-122">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb425-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="cb425-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cb425-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
