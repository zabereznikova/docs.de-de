---
title: ICLRTask::YieldTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
ms.openlocfilehash: 43f2048c8ab85fa7e94f73aad430400ad4c8352f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124593"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="94fa4-102">ICLRTask::YieldTask-Methode</span><span class="sxs-lookup"><span data-stu-id="94fa4-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="94fa4-103">Fordert an, dass die Common Language Runtime (CLR) die Aufgabe, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt, außer Kraft setzen und die Prozessorzeit für andere Tasks verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="94fa4-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fa4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94fa4-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="94fa4-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="94fa4-105">Return Value</span></span>  
  
|<span data-ttu-id="94fa4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94fa4-106">HRESULT</span></span>|<span data-ttu-id="94fa4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94fa4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94fa4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="94fa4-108">S_OK</span></span>|<span data-ttu-id="94fa4-109">`YieldTask` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94fa4-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="94fa4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94fa4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94fa4-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="94fa4-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94fa4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94fa4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94fa4-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="94fa4-113">The call timed out.</span></span>|  
|<span data-ttu-id="94fa4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94fa4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94fa4-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="94fa4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94fa4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94fa4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94fa4-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="94fa4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94fa4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94fa4-118">E_FAIL</span></span>|<span data-ttu-id="94fa4-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="94fa4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94fa4-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="94fa4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94fa4-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="94fa4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94fa4-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94fa4-122">Remarks</span></span>  
 <span data-ttu-id="94fa4-123">Ein Host ruft `YieldTask` auf, um Prozessorressourcen für andere Tasks oder Prozesse anzufordern.</span><span class="sxs-lookup"><span data-stu-id="94fa4-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="94fa4-124">Diese Methode ist primär dafür gedacht, Code mit langer Ausführungszeit zu ermöglichen, die CPU-Zeit zu Verb legen.</span><span class="sxs-lookup"><span data-stu-id="94fa4-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="94fa4-125">Die Laufzeit versucht, die Aufgabe, die die aktuelle `ICLRTask` Instanz darstellt, in einem Zustand zu platzieren, in dem Sie die Verarbeitungszeit erzielen kann, aber keine Garantie für Erfolg hat.</span><span class="sxs-lookup"><span data-stu-id="94fa4-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fa4-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94fa4-126">Requirements</span></span>  
 <span data-ttu-id="94fa4-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94fa4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fa4-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="94fa4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94fa4-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="94fa4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94fa4-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fa4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fa4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94fa4-131">See also</span></span>

- [<span data-ttu-id="94fa4-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94fa4-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="94fa4-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94fa4-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="94fa4-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94fa4-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="94fa4-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94fa4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
