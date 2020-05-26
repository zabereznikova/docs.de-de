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
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803691"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="d5112-102">IHostSemaphore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5112-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="d5112-103">Stellt die Host Implementierung eines Semaphors für das Threading dar.</span><span class="sxs-lookup"><span data-stu-id="d5112-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5112-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d5112-104">Methods</span></span>  
  
|<span data-ttu-id="d5112-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d5112-105">Method</span></span>|<span data-ttu-id="d5112-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5112-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5112-107">ReleaseSemaphore-Methode</span><span class="sxs-lookup"><span data-stu-id="d5112-107">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="d5112-108">Erhöht die Anzahl der aktuellen `IHostSemaphore` Instanz um den angegebenen Betrag.</span><span class="sxs-lookup"><span data-stu-id="d5112-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="d5112-109">Wait-Methode</span><span class="sxs-lookup"><span data-stu-id="d5112-109">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="d5112-110">Bewirkt, dass die aktuelle `IHostSemaphore` Instanz wartet, bis Sie im Besitz ist oder die angegebene Zeitspanne verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="d5112-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5112-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5112-111">Requirements</span></span>  
 <span data-ttu-id="d5112-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5112-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5112-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d5112-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5112-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d5112-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5112-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5112-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5112-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5112-116">See also</span></span>

- [<span data-ttu-id="d5112-117">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5112-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d5112-118">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5112-118">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="d5112-119">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5112-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="d5112-120">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5112-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="d5112-121">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d5112-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
