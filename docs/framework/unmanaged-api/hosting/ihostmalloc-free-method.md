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
ms.openlocfilehash: f7ae4e4cbb757edea242c57720baeb70ced5c428
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192056"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="710bf-102">IHostMAlloc::Free-Methode</span><span class="sxs-lookup"><span data-stu-id="710bf-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="710bf-103">Gibt Arbeitsspeicher frei, der mithilfe der [Zuordnungs](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) Funktion zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="710bf-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="710bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="710bf-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="710bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="710bf-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="710bf-106">in Ein Zeiger auf den Speicher, der freigegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="710bf-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="710bf-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="710bf-107">Return Value</span></span>  
  
|<span data-ttu-id="710bf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="710bf-108">HRESULT</span></span>|<span data-ttu-id="710bf-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="710bf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="710bf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="710bf-110">S_OK</span></span>|<span data-ttu-id="710bf-111">`Free` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="710bf-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="710bf-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="710bf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="710bf-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="710bf-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="710bf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="710bf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="710bf-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="710bf-115">The call timed out.</span></span>|  
|<span data-ttu-id="710bf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="710bf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="710bf-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="710bf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="710bf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="710bf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="710bf-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="710bf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="710bf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="710bf-120">E_FAIL</span></span>|<span data-ttu-id="710bf-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="710bf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="710bf-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="710bf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="710bf-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="710bf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="710bf-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="710bf-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="710bf-125">Es wurde versucht, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="710bf-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="710bf-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="710bf-126">Remarks</span></span>  
 <span data-ttu-id="710bf-127">Wenn der `pMem`-Parameter auf einen Speicherbereich verweist, der nicht mithilfe eines Aufrufes `Alloc`zugeordnet wurde, sollte der Host HOST_E_INVALIDOPERATION zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="710bf-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="710bf-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="710bf-128">Requirements</span></span>  
 <span data-ttu-id="710bf-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="710bf-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="710bf-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="710bf-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="710bf-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="710bf-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="710bf-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="710bf-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710bf-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="710bf-133">See also</span></span>

- [<span data-ttu-id="710bf-134">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="710bf-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="710bf-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="710bf-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
