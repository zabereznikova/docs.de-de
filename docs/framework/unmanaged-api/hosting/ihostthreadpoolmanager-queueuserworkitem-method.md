---
title: IHostThreadPoolManager::QueueUserWorkItem-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.QueueUserWorkItem
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9948673d6988de21c83c37538fb4d7c030296e58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="9817d-102">IHostThreadPoolManager::QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="9817d-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="9817d-103">Fügt eine Funktion für die Ausführung der Warteschlange hinzu und gibt ein Objekt mit Daten, die von dieser Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9817d-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="9817d-104">Die Funktion ausgeführt wird, wenn ein Thread verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9817d-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9817d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9817d-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9817d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9817d-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="9817d-107">[in] Ein Funktionszeiger, der zum Ausführen der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="9817d-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="9817d-108">[in] Ein Objekt, das Daten enthält, auf die von zu verwendenden `Function`.</span><span class="sxs-lookup"><span data-stu-id="9817d-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="9817d-109">[in] Eines der Flags Werte gemäß der Definition für die Win32- `QueueUserWorkItem` Methode, die Ausführung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="9817d-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9817d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9817d-110">Return Value</span></span>  
  
|<span data-ttu-id="9817d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9817d-111">HRESULT</span></span>|<span data-ttu-id="9817d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9817d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9817d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9817d-113">S_OK</span></span>|<span data-ttu-id="9817d-114">`QueueUserWorkItem`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9817d-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="9817d-115">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="9817d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9817d-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9817d-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9817d-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9817d-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9817d-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9817d-118">The call timed out.</span></span>|  
|<span data-ttu-id="9817d-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9817d-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9817d-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9817d-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9817d-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9817d-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9817d-122">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9817d-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9817d-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9817d-123">E_FAIL</span></span>|<span data-ttu-id="9817d-124">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9817d-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9817d-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="9817d-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9817d-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9817d-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9817d-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9817d-127">Remarks</span></span>  
 <span data-ttu-id="9817d-128">`QueueUserWorkItem`eine Arbeitsaufgabe zu einem Arbeitsthread im Threadpool die Warteschlange gestellt.</span><span class="sxs-lookup"><span data-stu-id="9817d-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="9817d-129">Die Signatur und Parametertypen sind identisch mit denen die entsprechenden Win32-Funktion, die den gleichen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="9817d-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="9817d-130">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="9817d-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9817d-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9817d-131">Requirements</span></span>  
 <span data-ttu-id="9817d-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9817d-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9817d-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9817d-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9817d-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9817d-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9817d-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9817d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9817d-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9817d-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="9817d-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9817d-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
