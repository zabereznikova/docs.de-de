---
title: ICLRGCManager::Collect-Methode
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
ms.openlocfilehash: 90ce4e888ddb3a10dd0dfd7e68463311db86742f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677764"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="97a78-102">ICLRGCManager::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="97a78-102">ICLRGCManager::Collect Method</span></span>

<span data-ttu-id="97a78-103">Erzwingt eine Garbage Collection für die angegebene Generierung.</span><span class="sxs-lookup"><span data-stu-id="97a78-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97a78-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97a78-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="97a78-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="97a78-106">in Die zu sammelnde Generation.</span><span class="sxs-lookup"><span data-stu-id="97a78-106">[in] The generation to collect.</span></span> <span data-ttu-id="97a78-107">Der Wert-1 erzwingt eine Auflistung aller Generationen.</span><span class="sxs-lookup"><span data-stu-id="97a78-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97a78-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="97a78-108">Return Value</span></span>  
  
|<span data-ttu-id="97a78-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97a78-109">HRESULT</span></span>|<span data-ttu-id="97a78-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97a78-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="97a78-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="97a78-111">S_OK</span></span>|<span data-ttu-id="97a78-112">`Collect` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="97a78-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="97a78-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="97a78-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="97a78-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="97a78-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="97a78-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="97a78-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="97a78-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="97a78-116">The call timed out.</span></span>|  
|<span data-ttu-id="97a78-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="97a78-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="97a78-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="97a78-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="97a78-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="97a78-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="97a78-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="97a78-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="97a78-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="97a78-121">E_FAIL</span></span>|<span data-ttu-id="97a78-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="97a78-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="97a78-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="97a78-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="97a78-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="97a78-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97a78-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97a78-125">Remarks</span></span>  

 <span data-ttu-id="97a78-126">Die `Collect` -Methode erzwingt, dass die CLR-Garbage Collector eine Auflistung unabhängig vom aktuellen Zustand ausführen.</span><span class="sxs-lookup"><span data-stu-id="97a78-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97a78-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="97a78-127">Requirements</span></span>  

 <span data-ttu-id="97a78-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97a78-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97a78-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="97a78-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97a78-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="97a78-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97a78-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97a78-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a78-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97a78-132">See also</span></span>

- [<span data-ttu-id="97a78-133">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="97a78-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="97a78-134">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="97a78-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="97a78-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97a78-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="97a78-136">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97a78-136">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="97a78-137">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="97a78-137">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="97a78-138">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="97a78-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="97a78-139">Hosting</span><span class="sxs-lookup"><span data-stu-id="97a78-139">Hosting</span></span>](index.md)
