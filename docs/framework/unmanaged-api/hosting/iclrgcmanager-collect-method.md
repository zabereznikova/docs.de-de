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
ms.openlocfilehash: aa906e314c408b7653e611b07d7ad21d4519b715
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616982"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="06ad2-102">ICLRGCManager::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="06ad2-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="06ad2-103">Erzwingt eine Garbage Collection für die angegebene Generierung.</span><span class="sxs-lookup"><span data-stu-id="06ad2-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ad2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06ad2-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06ad2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06ad2-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="06ad2-106">in Die zu sammelnde Generation.</span><span class="sxs-lookup"><span data-stu-id="06ad2-106">[in] The generation to collect.</span></span> <span data-ttu-id="06ad2-107">Der Wert-1 erzwingt eine Auflistung aller Generationen.</span><span class="sxs-lookup"><span data-stu-id="06ad2-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06ad2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06ad2-108">Return Value</span></span>  
  
|<span data-ttu-id="06ad2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06ad2-109">HRESULT</span></span>|<span data-ttu-id="06ad2-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="06ad2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06ad2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="06ad2-111">S_OK</span></span>|<span data-ttu-id="06ad2-112">`Collect`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06ad2-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="06ad2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06ad2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06ad2-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="06ad2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="06ad2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="06ad2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="06ad2-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="06ad2-116">The call timed out.</span></span>|  
|<span data-ttu-id="06ad2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="06ad2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="06ad2-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="06ad2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="06ad2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="06ad2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="06ad2-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="06ad2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="06ad2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06ad2-121">E_FAIL</span></span>|<span data-ttu-id="06ad2-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="06ad2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06ad2-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06ad2-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="06ad2-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="06ad2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06ad2-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06ad2-125">Remarks</span></span>  
 <span data-ttu-id="06ad2-126">Die `Collect` -Methode erzwingt, dass die CLR-Garbage Collector eine Auflistung unabhängig vom aktuellen Zustand ausführen.</span><span class="sxs-lookup"><span data-stu-id="06ad2-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06ad2-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06ad2-127">Requirements</span></span>  
 <span data-ttu-id="06ad2-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06ad2-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ad2-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="06ad2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06ad2-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="06ad2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06ad2-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ad2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ad2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06ad2-132">See also</span></span>

- [<span data-ttu-id="06ad2-133">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="06ad2-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="06ad2-134">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="06ad2-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="06ad2-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06ad2-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="06ad2-136">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06ad2-136">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="06ad2-137">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="06ad2-137">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="06ad2-138">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="06ad2-138">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="06ad2-139">Hosting</span><span class="sxs-lookup"><span data-stu-id="06ad2-139">Hosting</span></span>](index.md)
