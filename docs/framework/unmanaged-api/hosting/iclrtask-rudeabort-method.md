---
title: ICLRTask::RudeAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a99bda7a6d21fea159c8f616f2db7d12b1f27579
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435413"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="590d0-102">ICLRTask::RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="590d0-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="590d0-103">Weist die common Language Runtime (CLR) zum Abbrechen der Aufgabe, die vom aktuellen [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz sofort und ohne Bedingung.</span><span class="sxs-lookup"><span data-stu-id="590d0-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="590d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="590d0-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="590d0-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="590d0-105">Return Value</span></span>  
  
|<span data-ttu-id="590d0-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="590d0-106">HRESULT</span></span>|<span data-ttu-id="590d0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="590d0-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="590d0-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="590d0-108">S_OK</span></span>|<span data-ttu-id="590d0-109">`RudeAbort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="590d0-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="590d0-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="590d0-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="590d0-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="590d0-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="590d0-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="590d0-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="590d0-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="590d0-113">The call timed out.</span></span>|  
|<span data-ttu-id="590d0-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="590d0-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="590d0-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="590d0-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="590d0-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="590d0-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="590d0-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="590d0-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="590d0-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="590d0-118">E_FAIL</span></span>|<span data-ttu-id="590d0-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="590d0-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="590d0-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="590d0-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="590d0-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="590d0-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="590d0-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="590d0-122">Remarks</span></span>  
 <span data-ttu-id="590d0-123">Ein Host ruft `RudeAbort` sofort eine Aufgabe abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="590d0-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="590d0-124">Finalizer und Ausnahmebehandlungsroutinen sind nicht unbedingt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="590d0-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="590d0-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="590d0-125">Requirements</span></span>  
 <span data-ttu-id="590d0-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="590d0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="590d0-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="590d0-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="590d0-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="590d0-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="590d0-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="590d0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="590d0-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="590d0-130">See Also</span></span>  
 [<span data-ttu-id="590d0-131">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="590d0-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="590d0-132">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="590d0-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="590d0-133">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="590d0-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="590d0-134">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="590d0-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
