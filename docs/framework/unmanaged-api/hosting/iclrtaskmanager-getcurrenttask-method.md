---
title: ICLRTaskManager::GetCurrentTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: af855e3ba47dc329a4fb722c3e13d5f1816beba4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723271"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="40984-102">ICLRTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="40984-102">ICLRTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="40984-103">Ruft die [ICLRTask](iclrtask-interface.md) -Instanz ab, die zurzeit auf dem Betriebssystem Thread ausgeführt wird, von dem aus der Methodenaufrufe stammt.</span><span class="sxs-lookup"><span data-stu-id="40984-103">Gets the [ICLRTask](iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40984-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40984-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40984-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40984-105">Parameters</span></span>  

 `ppTask`  
 <span data-ttu-id="40984-106">vorgenommen Ein Zeiger auf die Adresse einer `ICLRTask` Instanz, die derzeit auf dem Betriebssystem Thread ausgeführt wird, von dem der-Befehl stammt, oder NULL, wenn zurzeit kein Task in diesem Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="40984-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40984-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40984-107">Return Value</span></span>  
  
|<span data-ttu-id="40984-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40984-108">HRESULT</span></span>|<span data-ttu-id="40984-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40984-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40984-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="40984-110">S_OK</span></span>|<span data-ttu-id="40984-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="40984-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="40984-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40984-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40984-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="40984-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40984-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40984-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40984-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="40984-115">The call timed out.</span></span>|  
|<span data-ttu-id="40984-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40984-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40984-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="40984-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40984-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40984-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40984-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="40984-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40984-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40984-120">E_FAIL</span></span>|<span data-ttu-id="40984-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="40984-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40984-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="40984-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40984-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="40984-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40984-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40984-124">Remarks</span></span>  

 <span data-ttu-id="40984-125">Die- `ICLRTask` Instanz, auf die der- `ppTask` Parameter verweist, stellt die aktuell ausgeführte Aufgabe für die CLR dar.</span><span class="sxs-lookup"><span data-stu-id="40984-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="40984-126">Die- `ICLRTask` Instanz ist einer entsprechenden [IHostTask](ihosttask-interface.md) -Instanz zugeordnet, die die Aufgabe für den Host darstellt.</span><span class="sxs-lookup"><span data-stu-id="40984-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40984-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="40984-127">Requirements</span></span>  

 <span data-ttu-id="40984-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40984-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40984-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="40984-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40984-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="40984-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40984-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40984-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40984-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40984-132">See also</span></span>

- [<span data-ttu-id="40984-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40984-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="40984-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40984-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="40984-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40984-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="40984-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40984-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
