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
ms.openlocfilehash: e7750d50b772ff17cf9dcd05de2e2f34556714e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770479"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="0d3eb-102">ICLRTask::RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="0d3eb-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="0d3eb-103">Weist die common Language Runtime (CLR) zum Abbrechen der Aufgabe, die vom aktuellen [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz sofort und ohne Bedingung.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d3eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d3eb-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="0d3eb-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d3eb-105">Return Value</span></span>  
  
|<span data-ttu-id="0d3eb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d3eb-106">HRESULT</span></span>|<span data-ttu-id="0d3eb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d3eb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d3eb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d3eb-108">S_OK</span></span>|<span data-ttu-id="0d3eb-109">`RudeAbort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="0d3eb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d3eb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d3eb-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d3eb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d3eb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d3eb-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-113">The call timed out.</span></span>|  
|<span data-ttu-id="0d3eb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d3eb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d3eb-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d3eb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d3eb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d3eb-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d3eb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d3eb-118">E_FAIL</span></span>|<span data-ttu-id="0d3eb-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d3eb-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d3eb-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d3eb-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d3eb-122">Remarks</span></span>  
 <span data-ttu-id="0d3eb-123">Ein Host ruft `RudeAbort` eine Aufgabe sofort abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="0d3eb-124">Finalizer und Ausnahmebehandlungsroutinen werden nicht unbedingt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d3eb-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d3eb-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d3eb-125">Requirements</span></span>  
 <span data-ttu-id="0d3eb-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d3eb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d3eb-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d3eb-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d3eb-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0d3eb-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d3eb-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d3eb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d3eb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d3eb-130">See also</span></span>

- [<span data-ttu-id="0d3eb-131">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d3eb-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="0d3eb-132">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d3eb-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="0d3eb-133">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d3eb-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="0d3eb-134">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d3eb-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
