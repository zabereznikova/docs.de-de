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
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804595"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="15f56-102">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15f56-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="15f56-103">Stellt die Implementierung eines Hosts für ein manuelles Zurücksetzungs Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="15f56-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15f56-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="15f56-104">Methods</span></span>  
  
|<span data-ttu-id="15f56-105">Methode</span><span class="sxs-lookup"><span data-stu-id="15f56-105">Method</span></span>|<span data-ttu-id="15f56-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="15f56-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15f56-107">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="15f56-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="15f56-108">Setzt die aktuelle `IHostManualEvent` Instanz auf einen nicht signalisierten Zustand zurück.</span><span class="sxs-lookup"><span data-stu-id="15f56-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="15f56-109">Set-Methode</span><span class="sxs-lookup"><span data-stu-id="15f56-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="15f56-110">Legt die aktuelle `IHostManualEvent` Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="15f56-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="15f56-111">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="15f56-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="15f56-112">Bewirkt, dass die aktuelle `IHostManualEvent` Instanz wartet, bis Sie im Besitz ist oder eine angegebene Zeitspanne abläuft.</span><span class="sxs-lookup"><span data-stu-id="15f56-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15f56-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15f56-113">Requirements</span></span>  
 <span data-ttu-id="15f56-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f56-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f56-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="15f56-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15f56-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15f56-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15f56-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f56-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15f56-118">See also</span></span>

- [<span data-ttu-id="15f56-119">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15f56-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="15f56-120">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15f56-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="15f56-121">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15f56-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="15f56-122">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15f56-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="15f56-123">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="15f56-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
