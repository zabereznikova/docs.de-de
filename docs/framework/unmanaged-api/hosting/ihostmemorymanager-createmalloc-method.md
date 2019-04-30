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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 194e9b73610ccb7282babf266eea2968a4f035ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951740"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="499c8-102">IHostMemoryManager::CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="499c8-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="499c8-103">Ruft einen Schnittstellenzeiger auf ein [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) Instanz, zu Anforderungen für speicherbelegung aus einem Heap erstellt, die vom Host verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="499c8-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="499c8-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="499c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="499c8-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="499c8-106">[in] Eine Kombination von [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) Flags, die die Merkmale des Speichers gibt an, die zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="499c8-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="499c8-107">[out] Ein Zeiger auf die Adresse des ein `IHostMAlloc` Instanz, die vom Host bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="499c8-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="499c8-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="499c8-108">Return Value</span></span>  
  
|<span data-ttu-id="499c8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="499c8-109">HRESULT</span></span>|<span data-ttu-id="499c8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="499c8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="499c8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="499c8-111">S_OK</span></span>|<span data-ttu-id="499c8-112">`CreateMAlloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="499c8-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="499c8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="499c8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="499c8-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="499c8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="499c8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="499c8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="499c8-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="499c8-116">The call timed out.</span></span>|  
|<span data-ttu-id="499c8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="499c8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="499c8-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="499c8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="499c8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="499c8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="499c8-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="499c8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="499c8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="499c8-121">E_FAIL</span></span>|<span data-ttu-id="499c8-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="499c8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="499c8-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="499c8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="499c8-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="499c8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="499c8-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="499c8-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="499c8-126">Es war nicht genügend physischer Arbeitsspeicher verfügbar, um die Anforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="499c8-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="499c8-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="499c8-127">Remarks</span></span>  
 <span data-ttu-id="499c8-128">`CreateMAlloc` Gibt ein Objekt, das die CLR die zuordnungsanforderungen über den Host statt der standard-Win32-Funktionen vornehmen kann.</span><span class="sxs-lookup"><span data-stu-id="499c8-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499c8-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="499c8-129">Requirements</span></span>  
 <span data-ttu-id="499c8-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="499c8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499c8-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="499c8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="499c8-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="499c8-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="499c8-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499c8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499c8-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="499c8-134">See also</span></span>

- [<span data-ttu-id="499c8-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="499c8-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="499c8-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="499c8-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
