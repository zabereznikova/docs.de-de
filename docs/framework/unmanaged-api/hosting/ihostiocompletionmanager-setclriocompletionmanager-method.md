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
ms.openlocfilehash: a76e807e6b316fc4b904e3f085a17b00d6a11c73
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804696"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="2505b-102">IHostIoCompletionManager::SetCLRIoCompletionManager-Methode</span><span class="sxs-lookup"><span data-stu-id="2505b-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="2505b-103">Stellt dem Host einen Schnittstellen Zeiger für die [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) -Instanz bereit, die vom Common Language Runtime (CLR) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="2505b-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2505b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2505b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2505b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2505b-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="2505b-106">in Ein Schnittstellen Zeiger auf eine- `ICLRIoCompletionManager` Instanz, die von der CLR bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2505b-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2505b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2505b-107">Return Value</span></span>  
  
|<span data-ttu-id="2505b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2505b-108">HRESULT</span></span>|<span data-ttu-id="2505b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2505b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2505b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2505b-110">S_OK</span></span>|<span data-ttu-id="2505b-111">`SetCLRIoCompletionManager`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2505b-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="2505b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2505b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2505b-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2505b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2505b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2505b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2505b-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2505b-115">The call timed out.</span></span>|  
|<span data-ttu-id="2505b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2505b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2505b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2505b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2505b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2505b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2505b-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2505b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2505b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2505b-120">E_FAIL</span></span>|<span data-ttu-id="2505b-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2505b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2505b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="2505b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2505b-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2505b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2505b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2505b-124">Remarks</span></span>  
 <span data-ttu-id="2505b-125">Nachdem die CLR aufgerufen hat `SetCLRIoCompletionManager` , muss der Host [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) aufrufen, um die CLR zu benachrichtigen, wenn eine e/a-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2505b-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2505b-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2505b-126">Requirements</span></span>  
 <span data-ttu-id="2505b-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2505b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2505b-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2505b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2505b-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2505b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2505b-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2505b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2505b-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2505b-131">See also</span></span>

- [<span data-ttu-id="2505b-132">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2505b-132">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2505b-133">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2505b-133">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
