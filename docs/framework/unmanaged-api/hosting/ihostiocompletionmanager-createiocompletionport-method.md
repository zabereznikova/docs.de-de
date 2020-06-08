---
title: IHostIoCompletionManager::CreateIoCompletionPort-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
ms.openlocfilehash: 240712296254e02f4d268a00e1c15ef34f4519f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501544"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="2012e-102">IHostIoCompletionManager::CreateIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="2012e-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="2012e-103">Fordert an, dass der Host einen neuen e/a-Abschlussport erstellt.</span><span class="sxs-lookup"><span data-stu-id="2012e-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2012e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2012e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2012e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2012e-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="2012e-106">vorgenommen Ein Zeiger auf ein Handle für den neu erstellten e/a-Abschlussport oder 0 (null), wenn der Port nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="2012e-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2012e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2012e-107">Return Value</span></span>  
  
|<span data-ttu-id="2012e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2012e-108">HRESULT</span></span>|<span data-ttu-id="2012e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2012e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2012e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2012e-110">S_OK</span></span>|<span data-ttu-id="2012e-111">`CreateIoCompletionPort`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2012e-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="2012e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2012e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2012e-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2012e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2012e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2012e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2012e-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2012e-115">The call timed out.</span></span>|  
|<span data-ttu-id="2012e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2012e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2012e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2012e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2012e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2012e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2012e-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2012e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2012e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2012e-120">E_FAIL</span></span>|<span data-ttu-id="2012e-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2012e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2012e-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="2012e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2012e-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2012e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2012e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2012e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2012e-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="2012e-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2012e-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2012e-126">Remarks</span></span>  
 <span data-ttu-id="2012e-127">Die CLR ruft die- `CreateIoCompletionPort` Methode auf, um anzufordern, dass der Host einen neuen e/a-Abschlussport erstellt.</span><span class="sxs-lookup"><span data-stu-id="2012e-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="2012e-128">Er bindet e/a-Vorgänge an diesen Port, indem er die [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) -Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="2012e-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="2012e-129">Der Host meldet den Status zurück an die CLR, indem er [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)anruft.</span><span class="sxs-lookup"><span data-stu-id="2012e-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2012e-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2012e-130">Requirements</span></span>  
 <span data-ttu-id="2012e-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2012e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2012e-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2012e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2012e-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2012e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2012e-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2012e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2012e-135">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="2012e-135">See also</span></span>

- [<span data-ttu-id="2012e-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2012e-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2012e-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2012e-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
