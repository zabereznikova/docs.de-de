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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a55b62c7c71510435b980a4e5938c20628046f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763626"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="c6d10-102">ICLRTask::ExitTask-Methode</span><span class="sxs-lookup"><span data-stu-id="c6d10-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="c6d10-103">Benachrichtigt die common Language Runtime (CLR), die die Aufgabe von der aktuellen dargestellt [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz beendet wird und versucht, die den Task ordnungsgemäß heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="c6d10-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6d10-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c6d10-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c6d10-105">Return Value</span></span>  
  
|<span data-ttu-id="c6d10-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6d10-106">HRESULT</span></span>|<span data-ttu-id="c6d10-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6d10-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6d10-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6d10-108">S_OK</span></span>|<span data-ttu-id="c6d10-109">`ExitTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c6d10-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="c6d10-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6d10-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6d10-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c6d10-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6d10-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6d10-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6d10-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c6d10-113">The call timed out.</span></span>|  
|<span data-ttu-id="c6d10-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6d10-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6d10-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c6d10-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6d10-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6d10-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6d10-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c6d10-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6d10-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6d10-118">E_FAIL</span></span>|<span data-ttu-id="c6d10-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c6d10-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6d10-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c6d10-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6d10-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c6d10-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6d10-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6d10-122">Remarks</span></span>  
 <span data-ttu-id="c6d10-123">`ExitTask` versucht, ein fehlerfreies Herunterfahren der eine Aufgabe, ähnlich wie beim Trennen eines Threads von einer nicht verwalteten Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="c6d10-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d10-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6d10-124">Requirements</span></span>  
 <span data-ttu-id="c6d10-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6d10-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d10-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6d10-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6d10-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c6d10-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6d10-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d10-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d10-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6d10-129">See also</span></span>

- [<span data-ttu-id="c6d10-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6d10-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c6d10-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6d10-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c6d10-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6d10-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c6d10-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6d10-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
