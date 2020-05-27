---
title: IHostTaskManager::Sleep-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
ms.openlocfilehash: bb12547155383bb410f592018232ca6f688bab8a
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841905"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="c4fc9-102">IHostTaskManager::Sleep-Methode</span><span class="sxs-lookup"><span data-stu-id="c4fc9-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="c4fc9-103">Benachrichtigt den Host, dass die aktuelle Aufgabe in den Standbymodus wechselt.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4fc9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4fc9-104">Syntax</span></span>  
  
```cpp  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4fc9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4fc9-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="c4fc9-106">in Das Zeitintervall in Millisekunden, in dem der Thread in den Standbymodus versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="c4fc9-107">in Einer der [WAIT_OPTION](wait-option-enumeration.md) Enumerationswerte, der angibt, welche Aktion der Host durchführen soll, wenn diese Aktion blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4fc9-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c4fc9-108">Return Value</span></span>  
  
|<span data-ttu-id="c4fc9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4fc9-109">HRESULT</span></span>|<span data-ttu-id="c4fc9-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4fc9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4fc9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4fc9-111">S_OK</span></span>|<span data-ttu-id="c4fc9-112">`Sleep`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="c4fc9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4fc9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4fc9-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4fc9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4fc9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4fc9-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-116">The call timed out.</span></span>|  
|<span data-ttu-id="c4fc9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4fc9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4fc9-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4fc9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4fc9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4fc9-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4fc9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4fc9-121">E_FAIL</span></span>|<span data-ttu-id="c4fc9-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4fc9-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4fc9-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4fc9-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4fc9-125">Remarks</span></span>  
 <span data-ttu-id="c4fc9-126">Die CLR ruft in der Regel auf, `IHostTaskManager::Sleep` Wenn <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> von Benutzercode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c4fc9-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4fc9-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4fc9-127">Requirements</span></span>  
 <span data-ttu-id="c4fc9-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4fc9-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4fc9-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c4fc9-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4fc9-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c4fc9-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4fc9-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4fc9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fc9-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4fc9-132">See also</span></span>

- [<span data-ttu-id="c4fc9-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4fc9-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c4fc9-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4fc9-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c4fc9-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4fc9-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c4fc9-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4fc9-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
