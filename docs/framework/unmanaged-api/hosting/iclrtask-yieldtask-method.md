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
ms.openlocfilehash: 7b9b47daa96ffcb1f66b462ff8e227250c5a81ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720278"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="06b97-102">ICLRTask::YieldTask-Methode</span><span class="sxs-lookup"><span data-stu-id="06b97-102">ICLRTask::YieldTask Method</span></span>

<span data-ttu-id="06b97-103">Fordert an, dass die Common Language Runtime (CLR) die Aufgabe, die die aktuelle [ICLRTask](iclrtask-interface.md) -Instanz darstellt, außer Kraft setzen und die Prozessorzeit für andere Tasks verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="06b97-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06b97-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="06b97-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06b97-105">Return Value</span></span>  
  
|<span data-ttu-id="06b97-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06b97-106">HRESULT</span></span>|<span data-ttu-id="06b97-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="06b97-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06b97-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="06b97-108">S_OK</span></span>|<span data-ttu-id="06b97-109">`YieldTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06b97-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="06b97-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06b97-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06b97-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="06b97-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="06b97-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="06b97-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="06b97-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="06b97-113">The call timed out.</span></span>|  
|<span data-ttu-id="06b97-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="06b97-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="06b97-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="06b97-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="06b97-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="06b97-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="06b97-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="06b97-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="06b97-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06b97-118">E_FAIL</span></span>|<span data-ttu-id="06b97-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="06b97-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06b97-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="06b97-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="06b97-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="06b97-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06b97-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06b97-122">Remarks</span></span>  

 <span data-ttu-id="06b97-123">Ein Host ruft `YieldTask` auf, um Prozessorressourcen für andere Tasks oder Prozesse anzufordern.</span><span class="sxs-lookup"><span data-stu-id="06b97-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="06b97-124">Diese Methode ist primär dafür gedacht, Code mit langer Ausführungszeit zu ermöglichen, die CPU-Zeit zu Verb legen.</span><span class="sxs-lookup"><span data-stu-id="06b97-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="06b97-125">Die Laufzeit versucht, die Aufgabe, die die aktuelle `ICLRTask` Instanz darstellt, in einem Zustand zu platzieren, in dem Sie Verarbeitungszeit erzeugen kann, jedoch keine Garantie für Erfolg hat.</span><span class="sxs-lookup"><span data-stu-id="06b97-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b97-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="06b97-126">Requirements</span></span>  

 <span data-ttu-id="06b97-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06b97-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b97-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="06b97-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06b97-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="06b97-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06b97-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b97-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b97-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06b97-131">See also</span></span>

- [<span data-ttu-id="06b97-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b97-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="06b97-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b97-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="06b97-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b97-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="06b97-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b97-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
