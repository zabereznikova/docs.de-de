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
ms.openlocfilehash: 10efe853c9a7ad7676058bc01b07063c557623d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699221"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="f2ae0-102">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2ae0-102">IHostTask Interface</span></span>

<span data-ttu-id="f2ae0-103">Stellt Methoden bereit, mit denen die Common Language Runtime (CLR) mit dem Host kommunizieren kann, um Aufgaben zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f2ae0-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2ae0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f2ae0-104">Methods</span></span>  
  
|<span data-ttu-id="f2ae0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f2ae0-105">Method</span></span>|<span data-ttu-id="f2ae0-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f2ae0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2ae0-107">Alert-Methode</span><span class="sxs-lookup"><span data-stu-id="f2ae0-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="f2ae0-108">Fordert an, dass der Host die Aufgabe reaktiviert, die von der aktuellen `IHostTask` Instanz dargestellt wird, sodass der Task abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2ae0-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="f2ae0-109">GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="f2ae0-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="f2ae0-110">Ruft die Thread Prioritäts Ebene der Aufgabe ab, die von der aktuellen-Instanz dargestellt wird `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="f2ae0-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="f2ae0-111">Join-Methode</span><span class="sxs-lookup"><span data-stu-id="f2ae0-111">Join Method</span></span>](ihosttask-join-method.md)|<span data-ttu-id="f2ae0-112">Blockiert die aufrufende Aufgabe, bis die von der aktuellen Instanz dargestellte Aufgabe `IHostTask` abgeschlossen ist, das angegebene Zeitintervall abgelaufen ist oder [IHostTask:: Alert](ihosttask-alert-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f2ae0-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="f2ae0-113">SetCLRTask-Methode</span><span class="sxs-lookup"><span data-stu-id="f2ae0-113">SetCLRTask Method</span></span>](ihosttask-setclrtask-method.md)|<span data-ttu-id="f2ae0-114">Ordnet der aktuellen Instanz eine [ICLRTask-Schnittstellen](iclrtask-interface.md) Instanz zu `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="f2ae0-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="f2ae0-115">SetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="f2ae0-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="f2ae0-116">Fordert an, dass der Host die Thread Prioritätsstufe für die Aufgabe anpasst, die durch die aktuelle Instanz dargestellt wird `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="f2ae0-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="f2ae0-117">Start-Methode</span><span class="sxs-lookup"><span data-stu-id="f2ae0-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="f2ae0-118">Fordert an, dass der Host die von der aktuellen Instanz dargestellte Aufgabe von einem angehaltenen `IHostTask` Zustand in einen Live-Zustand verschiebt, in dem Code ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2ae0-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2ae0-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2ae0-119">Remarks</span></span>  

 <span data-ttu-id="f2ae0-120">Die CLR ruft Methoden auf, die von definiert `IHostTask` werden, um eine Aufgabe zu starten, die Thread Prioritätsstufe festzulegen usw.</span><span class="sxs-lookup"><span data-stu-id="f2ae0-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2ae0-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f2ae0-121">Requirements</span></span>  

 <span data-ttu-id="f2ae0-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ae0-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ae0-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f2ae0-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2ae0-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f2ae0-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2ae0-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ae0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ae0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2ae0-126">See also</span></span>

- [<span data-ttu-id="f2ae0-127">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2ae0-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f2ae0-128">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2ae0-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f2ae0-129">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f2ae0-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="f2ae0-130">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f2ae0-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
