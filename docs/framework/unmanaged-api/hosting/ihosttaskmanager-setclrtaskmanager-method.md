---
title: IHostTaskManager::SetCLRTaskManager-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: 23d0679599c681468caa2507518d0ae3144ac26a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669795"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="90c3c-102">IHostTaskManager::SetCLRTaskManager-Methode</span><span class="sxs-lookup"><span data-stu-id="90c3c-102">IHostTaskManager::SetCLRTaskManager Method</span></span>

<span data-ttu-id="90c3c-103">Stellt dem Host einen Schnittstellen Zeiger auf eine [ICLRTaskManager](iclrtaskmanager-interface.md) -Instanz bereit, die vom Common Language Runtime (CLR) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="90c3c-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c3c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90c3c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90c3c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90c3c-105">Parameters</span></span>  

 `pManager`  
 <span data-ttu-id="90c3c-106">in Ein Zeiger auf eine- `ICLRTaskManager` Instanz, die von der Common Language Runtime implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="90c3c-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90c3c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="90c3c-107">Return Value</span></span>  
  
|<span data-ttu-id="90c3c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90c3c-108">HRESULT</span></span>|<span data-ttu-id="90c3c-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90c3c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90c3c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="90c3c-110">S_OK</span></span>|<span data-ttu-id="90c3c-111">`SetCLRTaskManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90c3c-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="90c3c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="90c3c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="90c3c-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="90c3c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="90c3c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="90c3c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="90c3c-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="90c3c-115">The call timed out.</span></span>|  
|<span data-ttu-id="90c3c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="90c3c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="90c3c-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="90c3c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="90c3c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="90c3c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="90c3c-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="90c3c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="90c3c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="90c3c-120">E_FAIL</span></span>|<span data-ttu-id="90c3c-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="90c3c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="90c3c-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="90c3c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="90c3c-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="90c3c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90c3c-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90c3c-124">Remarks</span></span>  

 <span data-ttu-id="90c3c-125">Die Laufzeit ruft `SetCLRTaskManager` auf, um dem Host einen Schnittstellen Zeiger auf eine-Instanz bereitzustellen `ICLRTaskManager` .</span><span class="sxs-lookup"><span data-stu-id="90c3c-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90c3c-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="90c3c-126">Requirements</span></span>  

 <span data-ttu-id="90c3c-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90c3c-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90c3c-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="90c3c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90c3c-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="90c3c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90c3c-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90c3c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c3c-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90c3c-131">See also</span></span>

- [<span data-ttu-id="90c3c-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90c3c-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="90c3c-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90c3c-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="90c3c-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90c3c-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="90c3c-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90c3c-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
