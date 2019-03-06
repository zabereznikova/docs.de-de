---
title: IHostMAlloc::Free-Methode
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cf60d4e711d0c88b5fb8b4c213b19bdea564324
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477828"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="8243c-102">IHostMAlloc::Free-Methode</span><span class="sxs-lookup"><span data-stu-id="8243c-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="8243c-103">Arbeitsspeicher, die mit zugeordnet wurde freigegeben der [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="8243c-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8243c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8243c-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8243c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8243c-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="8243c-106">[in] Ein Zeiger auf den Arbeitsspeicher freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8243c-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8243c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8243c-107">Return Value</span></span>  
  
|<span data-ttu-id="8243c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8243c-108">HRESULT</span></span>|<span data-ttu-id="8243c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8243c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8243c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8243c-110">S_OK</span></span>|<span data-ttu-id="8243c-111">`Free` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8243c-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="8243c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8243c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8243c-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8243c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8243c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8243c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8243c-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8243c-115">The call timed out.</span></span>|  
|<span data-ttu-id="8243c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8243c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8243c-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8243c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8243c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8243c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8243c-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8243c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8243c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8243c-120">E_FAIL</span></span>|<span data-ttu-id="8243c-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8243c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8243c-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8243c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8243c-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8243c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8243c-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8243c-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8243c-125">Es wurde versucht, um Arbeitsspeicher freizugeben, die nicht über den Host zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="8243c-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8243c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8243c-126">Remarks</span></span>  
 <span data-ttu-id="8243c-127">Wenn die `pMem` Parameter verweist auf einen Bereich des Arbeitsspeichers, die nicht zugeordnet wurde, mit einem Aufruf von `Alloc`, der Host sollte HOST_E_INVALIDOPERATION zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8243c-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8243c-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8243c-128">Requirements</span></span>  
 <span data-ttu-id="8243c-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8243c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8243c-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8243c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8243c-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8243c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8243c-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8243c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8243c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8243c-133">See also</span></span>
- [<span data-ttu-id="8243c-134">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8243c-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="8243c-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8243c-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
