---
title: IHostTask-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992835"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="a33e7-102">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a33e7-102">IHostTask Interface</span></span>
<span data-ttu-id="a33e7-103">Enthält Methoden, die die common Language Runtime (CLR) für die Kommunikation mit dem Host zum Verwalten von Aufgaben zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a33e7-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a33e7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a33e7-104">Methods</span></span>  
  
|<span data-ttu-id="a33e7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a33e7-105">Method</span></span>|<span data-ttu-id="a33e7-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a33e7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a33e7-107">Alert-Methode</span><span class="sxs-lookup"><span data-stu-id="a33e7-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="a33e7-108">Fordert an, dass der Host die Aufgabe, die vom aktuellen wake `IHostTask` -Instanz, damit der Task abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a33e7-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="a33e7-109">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="a33e7-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="a33e7-110">Ruft die Prioritätsebene von der Aufgabe, die vom aktuellen `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="a33e7-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="a33e7-111">Join-Methode</span><span class="sxs-lookup"><span data-stu-id="a33e7-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="a33e7-112">Die aufrufende Aufgabe blockiert, bis die Aufgabe, die vom aktuellen `IHostTask` Instanz abgeschlossen wurde, wird das angegebene Zeitintervall abgelaufen ist, oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a33e7-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="a33e7-113">SetCLRTask-Methode</span><span class="sxs-lookup"><span data-stu-id="a33e7-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="a33e7-114">Ordnet eine [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz mit dem aktuellen `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="a33e7-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="a33e7-115">SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="a33e7-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="a33e7-116">Fordert an, dass der Host die Threadpriorität anzupassen, die für die Aufgabe, die vom aktuellen Ebene `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="a33e7-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="a33e7-117">Start-Methode</span><span class="sxs-lookup"><span data-stu-id="a33e7-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="a33e7-118">Fordert an, dass der Host verschieben Sie die Aufgabe, die vom aktuellen `IHostTask` Instanz aus dem angehaltenen Status in einen aktiven Zustand, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a33e7-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a33e7-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a33e7-119">Remarks</span></span>  
 <span data-ttu-id="a33e7-120">Ruft die CLR definierte Methoden `IHostTask` um eine Aufgabe zu beginnen, legen Sie die Priorität des Threads, Ebene, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="a33e7-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a33e7-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a33e7-121">Requirements</span></span>  
 <span data-ttu-id="a33e7-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a33e7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a33e7-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a33e7-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a33e7-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a33e7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a33e7-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a33e7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33e7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a33e7-126">See also</span></span>

- [<span data-ttu-id="a33e7-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a33e7-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a33e7-128">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a33e7-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a33e7-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a33e7-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="a33e7-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a33e7-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
