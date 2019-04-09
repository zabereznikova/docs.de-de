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
ms.openlocfilehash: bc8d936ac4fca704e7e3069209d8ff75d46b044d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113671"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="95dc3-102">ICLRTask::YieldTask-Methode</span><span class="sxs-lookup"><span data-stu-id="95dc3-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="95dc3-103">Fordert an, dass die common Language Runtime (CLR) die Aufgabe zurückstellt, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt, und stellen Sie die CPU-Zeit für andere Aufgaben verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95dc3-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95dc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95dc3-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="95dc3-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95dc3-105">Return Value</span></span>  
  
|<span data-ttu-id="95dc3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95dc3-106">HRESULT</span></span>|<span data-ttu-id="95dc3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95dc3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95dc3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="95dc3-108">S_OK</span></span>|`YieldTask` <span data-ttu-id="95dc3-109">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95dc3-109">returned successfully.</span></span>|  
|<span data-ttu-id="95dc3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95dc3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95dc3-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="95dc3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95dc3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95dc3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95dc3-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="95dc3-113">The call timed out.</span></span>|  
|<span data-ttu-id="95dc3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95dc3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95dc3-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="95dc3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95dc3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95dc3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95dc3-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="95dc3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95dc3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95dc3-118">E_FAIL</span></span>|<span data-ttu-id="95dc3-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="95dc3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95dc3-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95dc3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95dc3-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="95dc3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95dc3-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95dc3-122">Remarks</span></span>  
 <span data-ttu-id="95dc3-123">Ein Host ruft `YieldTask` auf Anforderung Prozessorressourcen für andere Aufgaben oder Prozesse.</span><span class="sxs-lookup"><span data-stu-id="95dc3-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="95dc3-124">Diese Methode wird in erster Linie langer Codes freizugeben, CPU-Zeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="95dc3-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="95dc3-125">Die Laufzeit versucht, versetzen die Aufgabe, die die aktuelle `ICLRTask` Instanz darstellt, in einem Zustand, in denen Verarbeitungszeit abgezogen werden kann, sondern stellt keine Garantie für Erfolg.</span><span class="sxs-lookup"><span data-stu-id="95dc3-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95dc3-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95dc3-126">Requirements</span></span>  
 <span data-ttu-id="95dc3-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95dc3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95dc3-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95dc3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95dc3-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="95dc3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="95dc3-130">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="95dc3-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95dc3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95dc3-131">See also</span></span>

- [<span data-ttu-id="95dc3-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95dc3-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="95dc3-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95dc3-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="95dc3-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95dc3-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="95dc3-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95dc3-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
