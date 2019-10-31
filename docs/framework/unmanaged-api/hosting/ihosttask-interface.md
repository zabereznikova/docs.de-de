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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121392"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="fcfc5-102">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcfc5-102">IHostTask Interface</span></span>
<span data-ttu-id="fcfc5-103">Stellt Methoden bereit, mit denen die Common Language Runtime (CLR) mit dem Host kommunizieren kann, um Aufgaben zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fcfc5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fcfc5-104">Methods</span></span>  
  
|<span data-ttu-id="fcfc5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fcfc5-105">Method</span></span>|<span data-ttu-id="fcfc5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fcfc5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcfc5-107">Alert-Methode</span><span class="sxs-lookup"><span data-stu-id="fcfc5-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="fcfc5-108">Fordert an, dass der Host die Aufgabe aktiviert, die von der aktuellen `IHostTask` Instanz dargestellt wird, sodass der Task abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="fcfc5-109">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="fcfc5-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="fcfc5-110">Ruft die Thread Prioritäts Ebene der Aufgabe ab, die durch die aktuelle `IHostTask`-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="fcfc5-111">Join-Methode</span><span class="sxs-lookup"><span data-stu-id="fcfc5-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="fcfc5-112">Blockiert die aufrufende Aufgabe, bis die durch die aktuelle `IHostTask` Instanz dargestellte Aufgabe abgeschlossen ist, das angegebene Zeitintervall abgelaufen ist oder [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="fcfc5-113">SetCLRTask-Methode</span><span class="sxs-lookup"><span data-stu-id="fcfc5-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="fcfc5-114">Ordnet der aktuellen `IHostTask` Instanz eine [ICLRTask-Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz zu.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="fcfc5-115">SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="fcfc5-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="fcfc5-116">Fordert an, dass der Host die Thread Prioritätsstufe für die Aufgabe anpasst, die durch die aktuelle `IHostTask`-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="fcfc5-117">Start-Methode</span><span class="sxs-lookup"><span data-stu-id="fcfc5-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="fcfc5-118">Fordert an, dass der Host die Aufgabe, die von der aktuellen `IHostTask` Instanz dargestellt wird, von einem angehaltenen Zustand in einen Live Zustand verschiebt, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcfc5-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcfc5-119">Remarks</span></span>  
 <span data-ttu-id="fcfc5-120">Die CLR ruft Methoden auf, die durch `IHostTask` definiert werden, um eine Aufgabe zu starten, die Thread Prioritätsstufe festzulegen usw.</span><span class="sxs-lookup"><span data-stu-id="fcfc5-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcfc5-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcfc5-121">Requirements</span></span>  
 <span data-ttu-id="fcfc5-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcfc5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcfc5-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fcfc5-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcfc5-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fcfc5-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcfc5-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcfc5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcfc5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcfc5-126">See also</span></span>

- [<span data-ttu-id="fcfc5-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcfc5-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="fcfc5-128">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcfc5-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="fcfc5-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fcfc5-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="fcfc5-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcfc5-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
