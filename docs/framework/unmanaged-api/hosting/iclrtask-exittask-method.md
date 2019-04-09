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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075878"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="75aa7-102">ICLRTask::ExitTask-Methode</span><span class="sxs-lookup"><span data-stu-id="75aa7-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="75aa7-103">Benachrichtigt die common Language Runtime (CLR), die die Aufgabe von der aktuellen dargestellt [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz beendet wird und versucht, die den Task ordnungsgemäß heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="75aa7-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75aa7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75aa7-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="75aa7-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="75aa7-105">Return Value</span></span>  
  
|<span data-ttu-id="75aa7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75aa7-106">HRESULT</span></span>|<span data-ttu-id="75aa7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75aa7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75aa7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="75aa7-108">S_OK</span></span>|`ExitTask` <span data-ttu-id="75aa7-109">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="75aa7-109">returned successfully.</span></span>|  
|<span data-ttu-id="75aa7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="75aa7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="75aa7-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="75aa7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="75aa7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="75aa7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="75aa7-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="75aa7-113">The call timed out.</span></span>|  
|<span data-ttu-id="75aa7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="75aa7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="75aa7-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="75aa7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="75aa7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="75aa7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="75aa7-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="75aa7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="75aa7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75aa7-118">E_FAIL</span></span>|<span data-ttu-id="75aa7-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="75aa7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="75aa7-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75aa7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="75aa7-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="75aa7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75aa7-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75aa7-122">Remarks</span></span>  
 `ExitTask` <span data-ttu-id="75aa7-123">versucht, ein fehlerfreies Herunterfahren der eine Aufgabe, ähnlich wie beim Trennen eines Threads von einer nicht verwalteten Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="75aa7-123">attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75aa7-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75aa7-124">Requirements</span></span>  
 <span data-ttu-id="75aa7-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75aa7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75aa7-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="75aa7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75aa7-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="75aa7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="75aa7-128">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="75aa7-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75aa7-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75aa7-129">See also</span></span>

- [<span data-ttu-id="75aa7-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75aa7-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="75aa7-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75aa7-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="75aa7-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75aa7-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="75aa7-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75aa7-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
