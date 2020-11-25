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
ms.openlocfilehash: 4537d367518dd80b2559f8ca058684e234ff7a91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730746"
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="22619-102">IHostThreadPoolManager::QueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="22619-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>

<span data-ttu-id="22619-103">Fügt eine Funktion zur Ausführung in die Warteschlange ein und gibt ein Objekt an, das von dieser Funktion zu verwendende Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="22619-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="22619-104">Die Funktion wird ausgeführt, wenn ein Thread verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="22619-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22619-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="22619-105">Syntax</span></span>  
  
```cpp  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22619-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="22619-106">Parameters</span></span>  

 `Function`  
 <span data-ttu-id="22619-107">in Ein Funktionszeiger, der die auszuführende Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="22619-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="22619-108">in Ein-Objekt, das Daten enthält, die von verwendet werden sollen `Function` .</span><span class="sxs-lookup"><span data-stu-id="22619-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="22619-109">in Einer der Flags-Werte, wie für die Win32- `QueueUserWorkItem` Methode definiert, die die Ausführung steuern.</span><span class="sxs-lookup"><span data-stu-id="22619-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22619-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22619-110">Return Value</span></span>  
  
|<span data-ttu-id="22619-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22619-111">HRESULT</span></span>|<span data-ttu-id="22619-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="22619-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22619-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="22619-113">S_OK</span></span>|<span data-ttu-id="22619-114">`QueueUserWorkItem` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="22619-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="22619-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22619-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22619-116">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="22619-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22619-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22619-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22619-118">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="22619-118">The call timed out.</span></span>|  
|<span data-ttu-id="22619-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22619-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22619-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="22619-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22619-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22619-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22619-122">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="22619-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22619-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22619-123">E_FAIL</span></span>|<span data-ttu-id="22619-124">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="22619-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22619-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="22619-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22619-126">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="22619-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22619-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22619-127">Remarks</span></span>  

 <span data-ttu-id="22619-128">`QueueUserWorkItem` Fügt eine Arbeitsaufgabe einem Arbeits Thread im Thread Pool in die Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="22619-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="22619-129">Die Signatur-und Parametertypen sind identisch mit denen der entsprechenden Win32-Funktion, die denselben Namen hat.</span><span class="sxs-lookup"><span data-stu-id="22619-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="22619-130">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="22619-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22619-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="22619-131">Requirements</span></span>  

 <span data-ttu-id="22619-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22619-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22619-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="22619-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22619-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="22619-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22619-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22619-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22619-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22619-136">See also</span></span>

- <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="22619-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22619-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
