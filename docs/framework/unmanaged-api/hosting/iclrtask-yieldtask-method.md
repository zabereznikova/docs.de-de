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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fde9586c1b3736b5db2c4814058dd23713dd34d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770329"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="c355b-102">ICLRTask::YieldTask-Methode</span><span class="sxs-lookup"><span data-stu-id="c355b-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="c355b-103">Fordert an, dass die common Language Runtime (CLR) die Aufgabe zurückstellt, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt, und stellen Sie die CPU-Zeit für andere Aufgaben verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c355b-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c355b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c355b-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c355b-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c355b-105">Return Value</span></span>  
  
|<span data-ttu-id="c355b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c355b-106">HRESULT</span></span>|<span data-ttu-id="c355b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c355b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c355b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c355b-108">S_OK</span></span>|<span data-ttu-id="c355b-109">`YieldTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c355b-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="c355b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c355b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c355b-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c355b-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c355b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c355b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c355b-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c355b-113">The call timed out.</span></span>|  
|<span data-ttu-id="c355b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c355b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c355b-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c355b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c355b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c355b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c355b-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c355b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c355b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c355b-118">E_FAIL</span></span>|<span data-ttu-id="c355b-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c355b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c355b-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c355b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c355b-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c355b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c355b-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c355b-122">Remarks</span></span>  
 <span data-ttu-id="c355b-123">Ein Host ruft `YieldTask` auf Anforderung Prozessorressourcen für andere Aufgaben oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="c355b-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="c355b-124">Diese Methode wird in erster Linie langer Codes freizugeben, CPU-Zeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c355b-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="c355b-125">Die Laufzeit versucht, versetzen die Aufgabe, die die aktuelle `ICLRTask` Instanz darstellt, in einem Zustand, in denen Verarbeitungszeit abgezogen werden kann, sondern stellt keine Garantie für Erfolg.</span><span class="sxs-lookup"><span data-stu-id="c355b-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c355b-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c355b-126">Requirements</span></span>  
 <span data-ttu-id="c355b-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c355b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c355b-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c355b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c355b-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c355b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c355b-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c355b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c355b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c355b-131">See also</span></span>

- [<span data-ttu-id="c355b-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c355b-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c355b-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c355b-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c355b-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c355b-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c355b-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c355b-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
