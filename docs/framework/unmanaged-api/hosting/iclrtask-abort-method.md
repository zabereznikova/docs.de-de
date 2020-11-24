---
title: ICLRTask::Abort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: aadbbb5fc6abd3829f14670e42149174f6ef238d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690849"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="109db-102">ICLRTask::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="109db-102">ICLRTask::Abort Method</span></span>

<span data-ttu-id="109db-103">Fordert an, dass die Common Language Runtime (CLR) den Task abbrechen, den die aktuelle [ICLRTask](iclrtask-interface.md) -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="109db-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="109db-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="109db-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="109db-105">Return Value</span></span>  
  
|<span data-ttu-id="109db-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="109db-106">HRESULT</span></span>|<span data-ttu-id="109db-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="109db-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="109db-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="109db-108">S_OK</span></span>|<span data-ttu-id="109db-109">`Abort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="109db-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="109db-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="109db-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="109db-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="109db-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="109db-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="109db-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="109db-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="109db-113">The call timed out.</span></span>|  
|<span data-ttu-id="109db-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="109db-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="109db-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="109db-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="109db-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="109db-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="109db-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="109db-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="109db-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="109db-118">E_FAIL</span></span>|<span data-ttu-id="109db-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="109db-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="109db-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="109db-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="109db-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="109db-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="109db-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="109db-122">Remarks</span></span>  

 <span data-ttu-id="109db-123">Die CLR löst eine aus, <xref:System.Threading.ThreadAbortException> Wenn der Host aufruft `Abort` .</span><span class="sxs-lookup"><span data-stu-id="109db-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="109db-124">Sie wird unmittelbar nach der Initialisierung der Ausnahme Informationen zurückgegeben, ohne darauf zu warten, dass Benutzercode (z. b. Finalizer oder Ausnahme Behandlungs Mechanismen) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="109db-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="109db-125">Aufrufe von werden `Abort` daher schnell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="109db-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="109db-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="109db-126">Requirements</span></span>  

 <span data-ttu-id="109db-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="109db-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="109db-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="109db-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="109db-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="109db-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="109db-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="109db-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="109db-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="109db-131">See also</span></span>

- [<span data-ttu-id="109db-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="109db-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="109db-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="109db-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="109db-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="109db-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="109db-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="109db-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
