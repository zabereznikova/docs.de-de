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
ms.openlocfilehash: 7fc431861ac8f5c0e47e12e688f4ca004313c062
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704447"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="2d68f-102">IHostSyncManager::CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="2d68f-102">IHostSyncManager::CreateMonitorEvent Method</span></span>

<span data-ttu-id="2d68f-103">Erstellt ein überwachtes Ereignis Objekt für automatisches Zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="2d68f-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d68f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d68f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d68f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d68f-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="2d68f-106">in Ein Cookie, das dem Ereignis Objekt zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d68f-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="2d68f-107">vorgenommen Ein Zeiger auf die Adresse einer [IHostAutoEvent](ihostautoevent-interface.md) -Instanz oder NULL, wenn das Ereignis Objekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="2d68f-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d68f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d68f-108">Return Value</span></span>  
  
|<span data-ttu-id="2d68f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d68f-109">HRESULT</span></span>|<span data-ttu-id="2d68f-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d68f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d68f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d68f-111">S_OK</span></span>|<span data-ttu-id="2d68f-112">`CreateMonitorEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d68f-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="2d68f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d68f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d68f-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2d68f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d68f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d68f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d68f-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2d68f-116">The call timed out.</span></span>|  
|<span data-ttu-id="2d68f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d68f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d68f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2d68f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d68f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d68f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d68f-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2d68f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d68f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d68f-121">E_FAIL</span></span>|<span data-ttu-id="2d68f-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2d68f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d68f-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="2d68f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d68f-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2d68f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d68f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2d68f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2d68f-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d68f-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d68f-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d68f-127">Remarks</span></span>  

 <span data-ttu-id="2d68f-128">`CreateMonitorEvent` Gibt einen zurück `IHostAutoEvent` , den die CLR in der Implementierung des verwalteten <xref:System.Threading.Monitor?displayProperty=nameWithType> Typs verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d68f-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="2d68f-129">Diese Methode spiegelt die Win32- `CreateEvent` Funktion mit dem Wert, der `false` für den-Parameter angegeben ist `bManualReset` .</span><span class="sxs-lookup"><span data-stu-id="2d68f-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="2d68f-130">Der Host kann das Cookie verwenden, um zu bestimmen, welche Aufgabe auf den Monitor wartet, indem die [ICLRSyncManager:: GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2d68f-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d68f-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d68f-131">Requirements</span></span>  

 <span data-ttu-id="2d68f-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d68f-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d68f-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2d68f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d68f-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2d68f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d68f-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d68f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d68f-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d68f-136">See also</span></span>

- [<span data-ttu-id="2d68f-137">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d68f-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="2d68f-138">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d68f-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="2d68f-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d68f-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
