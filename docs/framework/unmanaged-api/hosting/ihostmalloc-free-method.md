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
ms.openlocfilehash: d4c9048c89d55ed048a55a771572823905a056df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687136"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="961c2-102">IHostMAlloc::Free-Methode</span><span class="sxs-lookup"><span data-stu-id="961c2-102">IHostMAlloc::Free Method</span></span>

<span data-ttu-id="961c2-103">Gibt Arbeitsspeicher frei, der mithilfe der [Zuordnungs](ihostmalloc-alloc-method.md) Funktion zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="961c2-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="961c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="961c2-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="961c2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="961c2-105">Parameters</span></span>  

 `pMem`  
 <span data-ttu-id="961c2-106">in Ein Zeiger auf den Speicher, der freigegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="961c2-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="961c2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="961c2-107">Return Value</span></span>  
  
|<span data-ttu-id="961c2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="961c2-108">HRESULT</span></span>|<span data-ttu-id="961c2-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="961c2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="961c2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="961c2-110">S_OK</span></span>|<span data-ttu-id="961c2-111">`Free` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="961c2-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="961c2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="961c2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="961c2-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="961c2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="961c2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="961c2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="961c2-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="961c2-115">The call timed out.</span></span>|  
|<span data-ttu-id="961c2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="961c2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="961c2-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="961c2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="961c2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="961c2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="961c2-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="961c2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="961c2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="961c2-120">E_FAIL</span></span>|<span data-ttu-id="961c2-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="961c2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="961c2-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="961c2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="961c2-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="961c2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="961c2-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="961c2-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="961c2-125">Es wurde versucht, Arbeitsspeicher freizugeben, der nicht über den Host zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="961c2-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="961c2-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="961c2-126">Remarks</span></span>  

 <span data-ttu-id="961c2-127">Wenn der- `pMem` Parameter auf einen Speicherbereich verweist, der nicht mithilfe eines Aufrufes zugeordnet wurde `Alloc` , sollte der Host HOST_E_INVALIDOPERATION zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="961c2-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="961c2-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="961c2-128">Requirements</span></span>  

 <span data-ttu-id="961c2-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="961c2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="961c2-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="961c2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="961c2-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="961c2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="961c2-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="961c2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961c2-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="961c2-133">See also</span></span>

- [<span data-ttu-id="961c2-134">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="961c2-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="961c2-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="961c2-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
