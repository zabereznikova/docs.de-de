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
ms.openlocfilehash: 5b0e2265810b00fe0760d4e25c0f9904a96d9f2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691044"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="dc967-102">ICLRTask::RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="dc967-102">ICLRTask::RudeAbort Method</span></span>

<span data-ttu-id="dc967-103">Weist den Common Language Runtime (CLR) an, die Aufgabe, die von der aktuellen [ICLRTask-Schnittstellen](iclrtask-interface.md) Instanz dargestellt wird, sofort und bedingungslos abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="dc967-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc967-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc967-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="dc967-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dc967-105">Return Value</span></span>  
  
|<span data-ttu-id="dc967-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc967-106">HRESULT</span></span>|<span data-ttu-id="dc967-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dc967-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc967-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc967-108">S_OK</span></span>|<span data-ttu-id="dc967-109">`RudeAbort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc967-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="dc967-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc967-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc967-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dc967-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc967-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc967-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc967-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="dc967-113">The call timed out.</span></span>|  
|<span data-ttu-id="dc967-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc967-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc967-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dc967-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc967-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc967-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc967-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="dc967-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc967-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc967-118">E_FAIL</span></span>|<span data-ttu-id="dc967-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dc967-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc967-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="dc967-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc967-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dc967-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc967-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc967-122">Remarks</span></span>  

 <span data-ttu-id="dc967-123">Ein Host ruft `RudeAbort` auf, um eine Aufgabe sofort abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="dc967-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="dc967-124">Die Ausführung von Finalizern und Ausnahme Behandlungs Routinen ist nicht garantiert.</span><span class="sxs-lookup"><span data-stu-id="dc967-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc967-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dc967-125">Requirements</span></span>  

 <span data-ttu-id="dc967-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc967-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc967-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dc967-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc967-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc967-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc967-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc967-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc967-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc967-130">See also</span></span>

- [<span data-ttu-id="dc967-131">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc967-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="dc967-132">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc967-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="dc967-133">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc967-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="dc967-134">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc967-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
