---
title: IHostTask::GetPriority-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: e41fcf2f03b024c1b4ae0032c0ff025d6e2aa1c3
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842503"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="cfdd1-102">IHostTask::GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="cfdd1-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="cfdd1-103">Ruft die Thread Prioritäts Ebene der Aufgabe ab, die durch die aktuelle [IHostTask](ihosttask-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-103">Gets the thread priority level of the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfdd1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfdd1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfdd1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfdd1-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="cfdd1-106">vorgenommen Ein Zeiger auf eine ganze Zahl, die die Thread Prioritäts Ebene der Aufgabe angibt, die durch die aktuelle Instanz dargestellt wird `IHostTask` .</span><span class="sxs-lookup"><span data-stu-id="cfdd1-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfdd1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cfdd1-107">Return Value</span></span>  
  
|<span data-ttu-id="cfdd1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cfdd1-108">HRESULT</span></span>|<span data-ttu-id="cfdd1-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cfdd1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfdd1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cfdd1-110">S_OK</span></span>|<span data-ttu-id="cfdd1-111">`GetPriority`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="cfdd1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cfdd1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cfdd1-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cfdd1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cfdd1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cfdd1-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-115">The call timed out.</span></span>|  
|<span data-ttu-id="cfdd1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cfdd1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cfdd1-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cfdd1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cfdd1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cfdd1-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cfdd1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cfdd1-120">E_FAIL</span></span>|<span data-ttu-id="cfdd1-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cfdd1-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cfdd1-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfdd1-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfdd1-124">Remarks</span></span>  
 <span data-ttu-id="cfdd1-125">Werte der Thread Prioritäts Ebene werden von der Win32- `SetThreadPriority` Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="cfdd1-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfdd1-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfdd1-126">Requirements</span></span>  
 <span data-ttu-id="cfdd1-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfdd1-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfdd1-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cfdd1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfdd1-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cfdd1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfdd1-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfdd1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfdd1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfdd1-131">See also</span></span>

- [<span data-ttu-id="cfdd1-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfdd1-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="cfdd1-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfdd1-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="cfdd1-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfdd1-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="cfdd1-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfdd1-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
