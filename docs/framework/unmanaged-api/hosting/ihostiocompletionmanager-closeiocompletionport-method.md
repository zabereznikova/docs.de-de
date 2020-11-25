---
title: IHostIoCompletionManager::CloseIoCompletionPort-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
ms.openlocfilehash: a45f8ab6372776bece09e408bc9887bfaddb0955
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727366"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="2989a-102">IHostIoCompletionManager::CloseIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="2989a-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>

<span data-ttu-id="2989a-103">Fordert an, dass der Host einen Port schließt, der durch einen früheren Aufrufen von " [feateiocompletionport](ihostiocompletionmanager-createiocompletionport-method.md)" geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="2989a-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2989a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2989a-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2989a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2989a-105">Parameters</span></span>  

 `hPort`  
 <span data-ttu-id="2989a-106">in Das Handle des zu schließenden Ports.</span><span class="sxs-lookup"><span data-stu-id="2989a-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2989a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2989a-107">Return Value</span></span>  
  
|<span data-ttu-id="2989a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2989a-108">HRESULT</span></span>|<span data-ttu-id="2989a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2989a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2989a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2989a-110">S_OK</span></span>|<span data-ttu-id="2989a-111">`CloseIoCompletionPort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2989a-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="2989a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2989a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2989a-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2989a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2989a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2989a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2989a-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2989a-115">The call timed out.</span></span>|  
|<span data-ttu-id="2989a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2989a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2989a-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2989a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2989a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2989a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2989a-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2989a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2989a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2989a-120">E_FAIL</span></span>|<span data-ttu-id="2989a-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2989a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2989a-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="2989a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2989a-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2989a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2989a-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2989a-124">E_INVALIDARG</span></span>|<span data-ttu-id="2989a-125">Es wurde ein ungültiges Port handle übermittelt.</span><span class="sxs-lookup"><span data-stu-id="2989a-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2989a-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2989a-126">Remarks</span></span>  

 <span data-ttu-id="2989a-127">`hPort` muss ein Handle für einen Port sein, der von einem früheren-aufgerufene aufgerufen wurde `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="2989a-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2989a-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2989a-128">Requirements</span></span>  

 <span data-ttu-id="2989a-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2989a-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2989a-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2989a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2989a-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2989a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2989a-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2989a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2989a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2989a-133">See also</span></span>

- [<span data-ttu-id="2989a-134">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2989a-134">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2989a-135">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2989a-135">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
