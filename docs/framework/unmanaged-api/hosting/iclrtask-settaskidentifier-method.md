---
title: ICLRTask::SetTaskIdentifier-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
ms.openlocfilehash: d1f731e00d4917b997dfba392cb9b6ce2afc082e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690745"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="987c7-102">ICLRTask::SetTaskIdentifier-Methode</span><span class="sxs-lookup"><span data-stu-id="987c7-102">ICLRTask::SetTaskIdentifier Method</span></span>

<span data-ttu-id="987c7-103">Weist den Common Language Runtime (CLR) an, den angegebenen Bezeichnerwert der Aufgabe zuzuordnen, die durch die aktuelle [ICLRTask](iclrtask-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="987c7-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="987c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="987c7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="987c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="987c7-105">Parameters</span></span>  

 `Asked`  
 <span data-ttu-id="987c7-106">in Der eindeutige Bezeichner für den Common Language Runtime, der der durch die aktuelle Instanz dargestellten Aufgabe zugeordnet werden soll `ICLRTask` .</span><span class="sxs-lookup"><span data-stu-id="987c7-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="987c7-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="987c7-107">Return Value</span></span>  
  
|<span data-ttu-id="987c7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="987c7-108">HRESULT</span></span>|<span data-ttu-id="987c7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="987c7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="987c7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="987c7-110">S_OK</span></span>|<span data-ttu-id="987c7-111">`SetTaskIdentifier` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="987c7-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="987c7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="987c7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="987c7-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="987c7-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="987c7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="987c7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="987c7-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="987c7-115">The call timed out.</span></span>|  
|<span data-ttu-id="987c7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="987c7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="987c7-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="987c7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="987c7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="987c7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="987c7-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="987c7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="987c7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="987c7-120">E_FAIL</span></span>|<span data-ttu-id="987c7-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="987c7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="987c7-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="987c7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="987c7-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="987c7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="987c7-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="987c7-124">Remarks</span></span>  

 <span data-ttu-id="987c7-125">Der Host kann einem Task einen Bezeichner zuordnen, um die Integration der CLR und des Hosts in eine Debugumgebung zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="987c7-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="987c7-126">Der Bezeichner hat keine Bedeutung für die CLR.</span><span class="sxs-lookup"><span data-stu-id="987c7-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="987c7-127">Die CLR übergibt sie an eine Debugger-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="987c7-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="987c7-128">Der Debugger kann diesen Bezeichner verwenden, um eine CLR-Aufrufe einer Host-aufrufsliste zuzuordnen und die jeweiligen Ablauf Verfolgungs Informationen zu aktivieren, wenn Sie in der Benutzeroberfläche des Debuggers angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="987c7-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="987c7-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="987c7-129">Requirements</span></span>  

 <span data-ttu-id="987c7-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="987c7-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="987c7-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="987c7-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="987c7-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="987c7-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="987c7-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="987c7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987c7-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="987c7-134">See also</span></span>

- [<span data-ttu-id="987c7-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="987c7-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="987c7-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="987c7-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="987c7-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="987c7-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="987c7-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="987c7-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
