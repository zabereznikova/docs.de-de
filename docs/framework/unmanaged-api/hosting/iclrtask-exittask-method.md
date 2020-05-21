---
title: ICLRTask::ExitTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
ms.openlocfilehash: 9294f149e020cfb22512b4f110d64c5dabb5e777
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762447"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="60454-102">ICLRTask::ExitTask-Methode</span><span class="sxs-lookup"><span data-stu-id="60454-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="60454-103">Benachrichtigt den Common Language Runtime (CLR), dass die durch die aktuelle [ICLRTask](iclrtask-interface.md) -Instanz dargestellte Aufgabe beendet wird, und versucht, die Aufgabe ordnungsgemäß zu schließen.</span><span class="sxs-lookup"><span data-stu-id="60454-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60454-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60454-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="60454-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60454-105">Return Value</span></span>  
  
|<span data-ttu-id="60454-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60454-106">HRESULT</span></span>|<span data-ttu-id="60454-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60454-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60454-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="60454-108">S_OK</span></span>|<span data-ttu-id="60454-109">`ExitTask`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="60454-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="60454-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="60454-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="60454-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="60454-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="60454-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="60454-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="60454-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="60454-113">The call timed out.</span></span>|  
|<span data-ttu-id="60454-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="60454-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="60454-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="60454-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="60454-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="60454-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="60454-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="60454-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="60454-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="60454-118">E_FAIL</span></span>|<span data-ttu-id="60454-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="60454-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="60454-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="60454-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="60454-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="60454-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60454-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60454-122">Remarks</span></span>  
 <span data-ttu-id="60454-123">`ExitTask`versucht, eine Aufgabe ordnungsgemäß zu beenden, analog zum Trennen eines Threads von einer nicht verwalteten Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="60454-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60454-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="60454-124">Requirements</span></span>  
 <span data-ttu-id="60454-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60454-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60454-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="60454-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60454-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="60454-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60454-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60454-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60454-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60454-129">See also</span></span>

- [<span data-ttu-id="60454-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60454-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="60454-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60454-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="60454-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60454-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="60454-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60454-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
