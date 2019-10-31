---
title: IHostSyncManager::CreateMonitorEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192017"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="23543-102">IHostSyncManager::CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="23543-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="23543-103">Erstellt ein überwachtes Ereignis Objekt für automatisches Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="23543-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23543-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23543-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23543-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23543-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="23543-106">in Ein Cookie, das dem Ereignis Objekt zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="23543-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="23543-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) -Instanz oder NULL, wenn das Ereignis Objekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="23543-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23543-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23543-108">Return Value</span></span>  
  
|<span data-ttu-id="23543-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23543-109">HRESULT</span></span>|<span data-ttu-id="23543-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23543-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23543-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="23543-111">S_OK</span></span>|<span data-ttu-id="23543-112">`CreateMonitorEvent` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23543-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="23543-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23543-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23543-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="23543-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23543-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23543-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23543-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="23543-116">The call timed out.</span></span>|  
|<span data-ttu-id="23543-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23543-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23543-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="23543-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23543-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23543-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23543-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="23543-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23543-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23543-121">E_FAIL</span></span>|<span data-ttu-id="23543-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="23543-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23543-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23543-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23543-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="23543-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="23543-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="23543-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="23543-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23543-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23543-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23543-127">Remarks</span></span>  
 <span data-ttu-id="23543-128">`CreateMonitorEvent` gibt eine `IHostAutoEvent` zurück, die die CLR in der Implementierung des verwalteten <xref:System.Threading.Monitor?displayProperty=nameWithType> Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="23543-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="23543-129">Diese Methode spiegelt die Win32-`CreateEvent` Funktion mit dem Wert `false` für den `bManualReset`-Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="23543-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="23543-130">Der Host kann das Cookie verwenden, um zu bestimmen, welche Aufgabe auf den Monitor wartet, indem die [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="23543-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23543-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23543-131">Requirements</span></span>  
 <span data-ttu-id="23543-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23543-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23543-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="23543-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23543-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23543-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23543-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23543-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23543-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23543-136">See also</span></span>

- [<span data-ttu-id="23543-137">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23543-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="23543-138">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23543-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="23543-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23543-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
