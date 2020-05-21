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
ms.openlocfilehash: 5d6e19fe307373c2920fd60b04bff482b238c5c4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762954"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="23fb7-102">ICLRTask::RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="23fb7-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="23fb7-103">Weist den Common Language Runtime (CLR) an, die Aufgabe, die von der aktuellen [ICLRTask-Schnittstellen](iclrtask-interface.md) Instanz dargestellt wird, sofort und bedingungslos abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="23fb7-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23fb7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23fb7-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();
```  
  
## <a name="return-value"></a><span data-ttu-id="23fb7-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23fb7-105">Return Value</span></span>  
  
|<span data-ttu-id="23fb7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23fb7-106">HRESULT</span></span>|<span data-ttu-id="23fb7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="23fb7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23fb7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="23fb7-108">S_OK</span></span>|<span data-ttu-id="23fb7-109">`RudeAbort`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23fb7-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="23fb7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23fb7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23fb7-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="23fb7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23fb7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23fb7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23fb7-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="23fb7-113">The call timed out.</span></span>|  
|<span data-ttu-id="23fb7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23fb7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23fb7-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="23fb7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23fb7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23fb7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23fb7-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="23fb7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23fb7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23fb7-118">E_FAIL</span></span>|<span data-ttu-id="23fb7-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="23fb7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23fb7-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="23fb7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23fb7-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="23fb7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23fb7-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23fb7-122">Remarks</span></span>  
 <span data-ttu-id="23fb7-123">Ein Host ruft `RudeAbort` auf, um eine Aufgabe sofort abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="23fb7-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="23fb7-124">Die Ausführung von Finalizern und Ausnahme Behandlungs Routinen ist nicht garantiert.</span><span class="sxs-lookup"><span data-stu-id="23fb7-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23fb7-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="23fb7-125">Requirements</span></span>  
 <span data-ttu-id="23fb7-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23fb7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23fb7-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="23fb7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23fb7-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23fb7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23fb7-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23fb7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23fb7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23fb7-130">See also</span></span>

- [<span data-ttu-id="23fb7-131">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23fb7-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="23fb7-132">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23fb7-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="23fb7-133">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23fb7-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="23fb7-134">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23fb7-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
