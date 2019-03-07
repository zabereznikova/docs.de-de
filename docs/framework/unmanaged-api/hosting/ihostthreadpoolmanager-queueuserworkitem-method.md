---
title: IHostThreadPoolManager::QueueUserWorkItem-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.QueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03185f3f554c5454b23b0c72c42d68714488e6be
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501707"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="1128a-102">IHostThreadPoolManager::QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="1128a-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="1128a-103">Fügt eine Funktion für die Ausführung und gibt ein Objekt mit Daten, die von dieser Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1128a-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="1128a-104">Die Funktion ausgeführt wird, wenn ein Thread verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="1128a-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1128a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1128a-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1128a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1128a-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="1128a-107">[in] Ein Funktionszeiger, der zum Ausführen der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="1128a-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="1128a-108">[in] Ein Objekt, das Daten enthält, die von verwendet werden sollen `Function`.</span><span class="sxs-lookup"><span data-stu-id="1128a-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="1128a-109">[in] Einer der Flags, die Werte, für die Win32-gemäß `QueueUserWorkItem` Methode, die Ausführung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1128a-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1128a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1128a-110">Return Value</span></span>  
  
|<span data-ttu-id="1128a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1128a-111">HRESULT</span></span>|<span data-ttu-id="1128a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1128a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1128a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1128a-113">S_OK</span></span>|<span data-ttu-id="1128a-114">`QueueUserWorkItem` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1128a-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="1128a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1128a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1128a-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1128a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1128a-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1128a-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1128a-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1128a-118">The call timed out.</span></span>|  
|<span data-ttu-id="1128a-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1128a-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1128a-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1128a-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1128a-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1128a-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1128a-122">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1128a-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1128a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1128a-123">E_FAIL</span></span>|<span data-ttu-id="1128a-124">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1128a-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1128a-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1128a-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1128a-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1128a-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1128a-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1128a-127">Remarks</span></span>  
 <span data-ttu-id="1128a-128">`QueueUserWorkItem` Stellt eine Arbeitsaufgabe an einen Arbeitsthread im Threadpool der Warteschleife hinzu.</span><span class="sxs-lookup"><span data-stu-id="1128a-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="1128a-129">Die Signatur und Parametertypen sind identisch mit denen der entsprechenden Win32-Funktion, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="1128a-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="1128a-130">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="1128a-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1128a-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1128a-131">Requirements</span></span>  
 <span data-ttu-id="1128a-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1128a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1128a-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1128a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1128a-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1128a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1128a-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1128a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1128a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1128a-136">See also</span></span>
- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="1128a-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1128a-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
