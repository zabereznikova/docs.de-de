---
title: IHostMemoryManager::CreateMAlloc-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.CreateMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b4f8a23d03b3d839aeab5d2f571cb4f98f1ec5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="ace08-102">IHostMemoryManager::CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="ace08-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="ace08-103">Ruft einen Schnittstellenzeiger auf eine [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) -Instanz, die verwendet wird, um belegungsanforderungen aus einem Heap erstellt wird, durch den Host vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ace08-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ace08-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ace08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ace08-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="ace08-106">[in] Eine Kombination von [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) Flags, die die Merkmale des Arbeitsspeichers angibt, das zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="ace08-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="ace08-107">[out] Ein Zeiger auf die Adresse des ein `IHostMAlloc` Instanz, die vom Host bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ace08-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ace08-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ace08-108">Return Value</span></span>  
  
|<span data-ttu-id="ace08-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ace08-109">HRESULT</span></span>|<span data-ttu-id="ace08-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ace08-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ace08-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ace08-111">S_OK</span></span>|<span data-ttu-id="ace08-112">`CreateMAlloc`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ace08-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="ace08-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ace08-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ace08-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ace08-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ace08-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ace08-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ace08-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ace08-116">The call timed out.</span></span>|  
|<span data-ttu-id="ace08-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ace08-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ace08-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ace08-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ace08-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ace08-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ace08-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ace08-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ace08-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ace08-121">E_FAIL</span></span>|<span data-ttu-id="ace08-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ace08-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ace08-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ace08-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ace08-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ace08-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ace08-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ace08-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ace08-126">Nicht genügend physischer Arbeitsspeicher war für den Abschluss der zuordnungsanforderung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ace08-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ace08-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ace08-127">Remarks</span></span>  
 <span data-ttu-id="ace08-128">`CreateMAlloc`Gibt ein Objekt, das von der CLR belegungsanforderungen über den Host anstelle der standardmäßigen Win32-Funktionen machen kann.</span><span class="sxs-lookup"><span data-stu-id="ace08-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ace08-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ace08-129">Requirements</span></span>  
 <span data-ttu-id="ace08-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ace08-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ace08-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ace08-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ace08-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ace08-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ace08-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ace08-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace08-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ace08-134">See Also</span></span>  
 [<span data-ttu-id="ace08-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ace08-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="ace08-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ace08-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
