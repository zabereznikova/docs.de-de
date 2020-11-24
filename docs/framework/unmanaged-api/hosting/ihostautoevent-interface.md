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
ms.openlocfilehash: 6893b019c7e86d3f359cf64752d30f7896203786
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680860"
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="6e89f-102">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e89f-102">IHostAutoEvent Interface</span></span>

<span data-ttu-id="6e89f-103">Stellt eine Darstellung der Host Implementierung eines automatischen Zurücksetzungs Ereignisses bereit.</span><span class="sxs-lookup"><span data-stu-id="6e89f-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e89f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6e89f-104">Methods</span></span>  
  
|<span data-ttu-id="6e89f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6e89f-105">Method</span></span>|<span data-ttu-id="6e89f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e89f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e89f-107">Set-Methode</span><span class="sxs-lookup"><span data-stu-id="6e89f-107">Set Method</span></span>](ihostautoevent-set-method.md)|<span data-ttu-id="6e89f-108">Legt die aktuelle `IHostAutoEvent` Instanz auf einen signalisierten Zustand fest.</span><span class="sxs-lookup"><span data-stu-id="6e89f-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="6e89f-109">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="6e89f-109">Wait Method</span></span>](ihostautoevent-wait-method.md)|<span data-ttu-id="6e89f-110">Bewirkt, dass die aktuelle `IHostAutoEvent` Instanz wartet, bis das Ereignis im Besitz des Ereignisses ist oder eine angegebene Zeitspanne abläuft.</span><span class="sxs-lookup"><span data-stu-id="6e89f-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e89f-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6e89f-111">Requirements</span></span>  

 <span data-ttu-id="6e89f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e89f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e89f-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6e89f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e89f-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6e89f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e89f-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e89f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e89f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e89f-116">See also</span></span>

- [<span data-ttu-id="6e89f-117">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e89f-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="6e89f-118">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e89f-118">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="6e89f-119">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e89f-119">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="6e89f-120">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6e89f-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
