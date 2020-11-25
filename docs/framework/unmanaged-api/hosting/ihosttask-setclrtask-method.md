---
title: IHostTask::SetCLRTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: e6b9a4015a6139d6c8d7101fa7811c7ad9134e4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720463"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="24b55-102">IHostTask::SetCLRTask-Methode</span><span class="sxs-lookup"><span data-stu-id="24b55-102">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="24b55-103">Ordnet `ICLRTask` der aktuellen [IHostTask](ihosttask-interface.md) -Instanz eine Instanz zu.</span><span class="sxs-lookup"><span data-stu-id="24b55-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24b55-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24b55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="24b55-105">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="24b55-106">in Ein Schnittstellen Zeiger auf die- `ICLRTask` Instanz, die der aktuellen-Instanz zugeordnet werden soll `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="24b55-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24b55-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="24b55-107">Return Value</span></span>  
  
|<span data-ttu-id="24b55-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24b55-108">HRESULT</span></span>|<span data-ttu-id="24b55-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="24b55-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24b55-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="24b55-110">S_OK</span></span>|<span data-ttu-id="24b55-111">`SetCLRTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24b55-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="24b55-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="24b55-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="24b55-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="24b55-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="24b55-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="24b55-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="24b55-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="24b55-115">The call timed out.</span></span>|  
|<span data-ttu-id="24b55-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="24b55-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="24b55-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="24b55-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="24b55-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="24b55-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="24b55-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="24b55-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="24b55-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="24b55-120">E_FAIL</span></span>|<span data-ttu-id="24b55-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="24b55-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="24b55-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="24b55-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="24b55-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="24b55-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24b55-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24b55-124">Remarks</span></span>  

 <span data-ttu-id="24b55-125">Die CLR ruft `SetCLRTask` auf, um eine `ICLRTask` Instanz der aktuellen `IHostTask` Instanz zuzuordnen, die durch einen Aufruf von [IHostTaskManager:: kreatetask](ihosttaskmanager-createtask-method.md)erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="24b55-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24b55-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="24b55-126">Requirements</span></span>  

 <span data-ttu-id="24b55-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24b55-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24b55-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="24b55-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24b55-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="24b55-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24b55-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24b55-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b55-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24b55-131">See also</span></span>

- [<span data-ttu-id="24b55-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24b55-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="24b55-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24b55-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="24b55-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24b55-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="24b55-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24b55-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
