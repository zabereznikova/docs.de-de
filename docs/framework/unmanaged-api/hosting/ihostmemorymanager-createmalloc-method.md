---
title: IHostMemoryManager::CreateMAlloc-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 8bcb01f4a19e6043bd59fe6f1565cdf35ed1f77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136724"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="7b56e-102">IHostMemoryManager::CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="7b56e-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="7b56e-103">Ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz ab, die verwendet wird, um Zuordnungs Anforderungen von einem Heap zu erstellen, der vom Host erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7b56e-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b56e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b56e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b56e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b56e-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="7b56e-106">in Eine Kombination von [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) -Flags, die die Merkmale des zugeordneten Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="7b56e-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="7b56e-107">vorgenommen Ein Zeiger auf die Adresse einer `IHostMAlloc`-Instanz, die vom Host bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7b56e-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b56e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b56e-108">Return Value</span></span>  
  
|<span data-ttu-id="7b56e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b56e-109">HRESULT</span></span>|<span data-ttu-id="7b56e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b56e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b56e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b56e-111">S_OK</span></span>|<span data-ttu-id="7b56e-112">`CreateMAlloc` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7b56e-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="7b56e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7b56e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7b56e-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7b56e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7b56e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7b56e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7b56e-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7b56e-116">The call timed out.</span></span>|  
|<span data-ttu-id="7b56e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7b56e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7b56e-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7b56e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7b56e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7b56e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7b56e-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7b56e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7b56e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7b56e-121">E_FAIL</span></span>|<span data-ttu-id="7b56e-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7b56e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7b56e-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b56e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7b56e-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7b56e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7b56e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7b56e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7b56e-126">Zum Abschluss der Zuordnungs Anforderung war nicht genügend physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7b56e-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b56e-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b56e-127">Remarks</span></span>  
 <span data-ttu-id="7b56e-128">`CreateMAlloc` gibt ein-Objekt zurück, das der CLR ermöglicht, Zuordnungs Anforderungen über den Host zu senden, statt die Win32-Standardfunktionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b56e-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b56e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b56e-129">Requirements</span></span>  
 <span data-ttu-id="7b56e-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b56e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b56e-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7b56e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b56e-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7b56e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b56e-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b56e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b56e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b56e-134">See also</span></span>

- [<span data-ttu-id="7b56e-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b56e-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="7b56e-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b56e-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
