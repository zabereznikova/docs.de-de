---
title: ICLRTaskManager::CreateTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: 9829f57da911b43626516284e4858adc4139a3ca
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762876"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="81b89-102">ICLRTaskManager::CreateTask-Methode</span><span class="sxs-lookup"><span data-stu-id="81b89-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="81b89-103">Fordert explizit an, dass die Common Language Runtime (CLR) eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="81b89-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81b89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81b89-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81b89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="81b89-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="81b89-106">vorgenommen Ein Zeiger auf die Adresse eines neu erstellten [ICLRTask](iclrtask-interface.md)-Element oder NULL, wenn die Aufgabe nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="81b89-106">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81b89-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="81b89-107">Return Value</span></span>  
  
|<span data-ttu-id="81b89-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81b89-108">HRESULT</span></span>|<span data-ttu-id="81b89-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="81b89-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81b89-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="81b89-110">S_OK</span></span>|<span data-ttu-id="81b89-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81b89-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="81b89-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81b89-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81b89-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="81b89-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81b89-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81b89-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81b89-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="81b89-115">The call timed out.</span></span>|  
|<span data-ttu-id="81b89-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81b89-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81b89-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="81b89-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81b89-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81b89-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81b89-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="81b89-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81b89-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81b89-120">E_FAIL</span></span>|<span data-ttu-id="81b89-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="81b89-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81b89-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="81b89-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81b89-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="81b89-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="81b89-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="81b89-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="81b89-125">Es ist nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="81b89-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81b89-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81b89-126">Remarks</span></span>  
 <span data-ttu-id="81b89-127">Die CLR erstellt bei der Initialisierung automatisch eine neue Aufgabe, wenn Benutzercode einen Thread mithilfe von Typen im- <xref:System.Threading> Namespace oder durch Erhöhen der Größe des Thread Pools erstellt.</span><span class="sxs-lookup"><span data-stu-id="81b89-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="81b89-128">Außerdem werden Aufgaben erstellt, wenn von nicht verwaltetem Code eine verwaltete Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="81b89-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="81b89-129">`CreateTask`ermöglicht dem Host, eine explizite Anforderung zu erstellen, dass die CLR eine neue Aufgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="81b89-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="81b89-130">Beispielsweise kann der Host diese Methode aufrufen, um Datenstrukturen vorab zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="81b89-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="81b89-131">Die neue Aufgabe wird in einem angehaltenen Zustand zurückgegeben und bleibt angehalten, bis der Host [IHostTask:: Start](ihosttask-start-method.md)explizit aufruft.</span><span class="sxs-lookup"><span data-stu-id="81b89-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81b89-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="81b89-132">Requirements</span></span>  
 <span data-ttu-id="81b89-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81b89-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81b89-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="81b89-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81b89-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="81b89-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81b89-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81b89-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b89-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="81b89-137">See also</span></span>

- [<span data-ttu-id="81b89-138">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81b89-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="81b89-139">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81b89-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="81b89-140">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81b89-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="81b89-141">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81b89-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
