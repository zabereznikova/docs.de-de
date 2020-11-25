---
title: IHostIoCompletionManager::SetCLRIoCompletionManager-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
ms.openlocfilehash: d370cc81942269bd79e06e0fa57fe5d79832b3c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724844"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="1b626-102">IHostIoCompletionManager::SetCLRIoCompletionManager-Methode</span><span class="sxs-lookup"><span data-stu-id="1b626-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>

<span data-ttu-id="1b626-103">Stellt dem Host einen Schnittstellen Zeiger für die [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) -Instanz bereit, die vom Common Language Runtime (CLR) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="1b626-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b626-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b626-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b626-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b626-105">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="1b626-106">in Ein Schnittstellen Zeiger auf eine- `ICLRIoCompletionManager` Instanz, die von der CLR bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1b626-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b626-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b626-107">Return Value</span></span>  
  
|<span data-ttu-id="1b626-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b626-108">HRESULT</span></span>|<span data-ttu-id="1b626-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1b626-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b626-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b626-110">S_OK</span></span>|<span data-ttu-id="1b626-111">`SetCLRIoCompletionManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b626-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="1b626-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b626-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b626-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1b626-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b626-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b626-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b626-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1b626-115">The call timed out.</span></span>|  
|<span data-ttu-id="1b626-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b626-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b626-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1b626-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b626-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b626-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b626-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1b626-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b626-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b626-120">E_FAIL</span></span>|<span data-ttu-id="1b626-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b626-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b626-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="1b626-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b626-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1b626-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b626-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b626-124">Remarks</span></span>  

 <span data-ttu-id="1b626-125">Nachdem die CLR aufgerufen hat `SetCLRIoCompletionManager` , muss der Host [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) aufrufen, um die CLR zu benachrichtigen, wenn eine e/a-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1b626-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b626-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1b626-126">Requirements</span></span>  

 <span data-ttu-id="1b626-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b626-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b626-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1b626-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b626-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1b626-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b626-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b626-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b626-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b626-131">See also</span></span>

- [<span data-ttu-id="1b626-132">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b626-132">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="1b626-133">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b626-133">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
