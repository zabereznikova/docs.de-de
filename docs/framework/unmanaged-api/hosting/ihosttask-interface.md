---
title: IHostTask-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask
helpviewer_keywords: IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbffe2a171c112d4e9650b2c1b2a9ce1f010f382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttask-interface"></a><span data-ttu-id="6b3cd-102">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b3cd-102">IHostTask Interface</span></span>
<span data-ttu-id="6b3cd-103">Enthält Methoden, die die common Language Runtime (CLR) für die Kommunikation mit dem Host zum Verwalten von Aufgaben ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b3cd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6b3cd-104">Methods</span></span>  
  
|<span data-ttu-id="6b3cd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6b3cd-105">Method</span></span>|<span data-ttu-id="6b3cd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b3cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b3cd-107">Alert-Methode</span><span class="sxs-lookup"><span data-stu-id="6b3cd-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="6b3cd-108">Fordert an, dass der Host die Aufgabe, die vom aktuellen Wake-on `IHostTask` Instanz, damit der Task abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="6b3cd-109">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="6b3cd-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="6b3cd-110">Ruft die Prioritätsebene der Aufgabe, die vom aktuellen `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6b3cd-111">Join-Methode</span><span class="sxs-lookup"><span data-stu-id="6b3cd-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="6b3cd-112">Die aufrufende Aufgabe blockiert, bis die Aufgabe, die vom aktuellen `IHostTask` Instanz abgeschlossen hat, kann das angegebene Zeitintervall abläuft, oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="6b3cd-113">SetCLRTask-Methode</span><span class="sxs-lookup"><span data-stu-id="6b3cd-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="6b3cd-114">Ordnet eine [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit dem aktuellen `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6b3cd-115">SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="6b3cd-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="6b3cd-116">Fordert an, dass der Host die Threadpriorität anzupassen, die für die Aufgabe dargestellt, die von der aktuellen Ebene `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="6b3cd-117">Start-Methode</span><span class="sxs-lookup"><span data-stu-id="6b3cd-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="6b3cd-118">Fordert an, dass der Host die Aufgabe, die vom aktuellen verschieben `IHostTask` Instanz vom Zustand "angehalten" in einen aktiven Zustand, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b3cd-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b3cd-119">Remarks</span></span>  
 <span data-ttu-id="6b3cd-120">Die CLR ruft definierte Methoden `IHostTask` um eine Aufgabe zu starten, legen Sie die Threadpriorität Ebene, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="6b3cd-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b3cd-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b3cd-121">Requirements</span></span>  
 <span data-ttu-id="6b3cd-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b3cd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b3cd-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6b3cd-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b3cd-124">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6b3cd-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b3cd-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b3cd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3cd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b3cd-126">See Also</span></span>  
 [<span data-ttu-id="6b3cd-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b3cd-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="6b3cd-128">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b3cd-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6b3cd-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b3cd-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="6b3cd-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6b3cd-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
