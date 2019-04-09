---
title: ICLRTask::SwitchOut-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a215189461bd22011462842bf02ff6c0109119fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090041"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="7b2ac-102">ICLRTask::SwitchOut-Methode</span><span class="sxs-lookup"><span data-stu-id="7b2ac-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="7b2ac-103">Benachrichtigt die common Language Runtime (CLR), die die Aufgabe von der aktuellen dargestellt [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz ist nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b2ac-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7b2ac-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b2ac-105">Return Value</span></span>  
  
|<span data-ttu-id="7b2ac-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b2ac-106">HRESULT</span></span>|<span data-ttu-id="7b2ac-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b2ac-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b2ac-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b2ac-108">S_OK</span></span>|`SwitchOut` <span data-ttu-id="7b2ac-109">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-109">returned successfully.</span></span>|  
|<span data-ttu-id="7b2ac-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7b2ac-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7b2ac-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7b2ac-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7b2ac-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7b2ac-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-113">The call timed out.</span></span>|  
|<span data-ttu-id="7b2ac-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7b2ac-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7b2ac-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7b2ac-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7b2ac-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7b2ac-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7b2ac-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b2ac-118">E_FAIL</span></span>|<span data-ttu-id="7b2ac-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7b2ac-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7b2ac-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b2ac-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b2ac-122">Remarks</span></span>  
 <span data-ttu-id="7b2ac-123">Ein Host ruft `SwitchOut` um der CLR darüber zu informieren, dass das Ausführen des Tasks vorübergehend unterbrochen wurde, die die aktuelle `ICLRTask` -Instanz darstellt, und plant die Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="7b2ac-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b2ac-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b2ac-124">Requirements</span></span>  
 <span data-ttu-id="7b2ac-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b2ac-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2ac-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7b2ac-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b2ac-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7b2ac-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7b2ac-128">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7b2ac-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b2ac-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b2ac-129">See also</span></span>

- [<span data-ttu-id="7b2ac-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b2ac-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7b2ac-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b2ac-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7b2ac-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b2ac-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7b2ac-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b2ac-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
