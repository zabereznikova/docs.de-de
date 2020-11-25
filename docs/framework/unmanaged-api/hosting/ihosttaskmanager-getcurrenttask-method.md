---
title: IHostTaskManager::GetCurrentTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: 72b7f6e3a5a09bd06e8a7fbb94680ed3ea89b225
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727301"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="71578-102">IHostTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="71578-102">IHostTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="71578-103">Ruft einen Schnittstellen Zeiger auf die Aufgabe ab, die derzeit auf dem Betriebssystem Thread ausgeführt wird, von dem dieser aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="71578-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71578-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71578-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71578-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71578-105">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="71578-106">vorgenommen Ein Zeiger auf die Adresse einer [IHostTask](ihosttask-interface.md) -Instanz, die den derzeit ausgeführten Task darstellt, oder NULL, wenn derzeit keine Aufgabe ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="71578-106">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71578-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="71578-107">Return Value</span></span>  
  
|<span data-ttu-id="71578-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71578-108">HRESULT</span></span>|<span data-ttu-id="71578-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="71578-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71578-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71578-110">S_OK</span></span>|<span data-ttu-id="71578-111">`GetCurrentTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="71578-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="71578-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71578-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71578-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="71578-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71578-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71578-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71578-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="71578-115">The call timed out.</span></span>|  
|<span data-ttu-id="71578-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71578-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71578-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="71578-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71578-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71578-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71578-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="71578-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71578-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71578-120">E_FAIL</span></span>|<span data-ttu-id="71578-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="71578-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71578-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="71578-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71578-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="71578-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71578-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="71578-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="71578-125">`GetCurrentTask` wurde in einem Betriebssystem Thread außerhalb der Kontrolle des Hosts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="71578-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71578-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71578-126">Remarks</span></span>  

 <span data-ttu-id="71578-127">Der Host kann auch den- `pTask` Parameter auf NULL festlegen, um zu verhindern, dass eine Aufgabe, die nicht initiiert wurde, in die CLR wechselt.</span><span class="sxs-lookup"><span data-stu-id="71578-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71578-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71578-128">Requirements</span></span>  

 <span data-ttu-id="71578-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71578-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71578-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="71578-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71578-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="71578-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71578-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71578-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71578-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71578-133">See also</span></span>

- [<span data-ttu-id="71578-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71578-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="71578-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71578-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="71578-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71578-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="71578-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71578-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
