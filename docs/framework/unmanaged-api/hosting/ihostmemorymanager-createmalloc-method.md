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
ms.openlocfilehash: 79580170d544cd3763992a4bc67fd20e3446bb1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685720"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="ed706-102">IHostMemoryManager::CreateMAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="ed706-102">IHostMemoryManager::CreateMAlloc Method</span></span>

<span data-ttu-id="ed706-103">Ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](ihostmalloc-interface.md) -Instanz ab, die verwendet wird, um Zuordnungs Anforderungen von einem Heap zu erstellen, der vom Host erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ed706-103">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed706-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed706-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed706-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed706-105">Parameters</span></span>  

 `dwMallocType`  
 <span data-ttu-id="ed706-106">in Eine Kombination aus [MALLOC_TYPE](malloc-type-enumeration.md) Flags, die die Merkmale des zugeordneten Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="ed706-106">[in] A combination of [MALLOC_TYPE](malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="ed706-107">vorgenommen Ein Zeiger auf die Adresse einer- `IHostMAlloc` Instanz, die vom Host bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ed706-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed706-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ed706-108">Return Value</span></span>  
  
|<span data-ttu-id="ed706-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed706-109">HRESULT</span></span>|<span data-ttu-id="ed706-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ed706-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed706-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed706-111">S_OK</span></span>|<span data-ttu-id="ed706-112">`CreateMAlloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed706-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="ed706-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed706-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed706-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ed706-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed706-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed706-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed706-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ed706-116">The call timed out.</span></span>|  
|<span data-ttu-id="ed706-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed706-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed706-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ed706-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed706-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed706-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed706-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ed706-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed706-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed706-121">E_FAIL</span></span>|<span data-ttu-id="ed706-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ed706-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed706-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="ed706-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed706-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ed706-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed706-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ed706-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ed706-126">Zum Abschluss der Zuordnungs Anforderung war nicht genügend physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ed706-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed706-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed706-127">Remarks</span></span>  

 <span data-ttu-id="ed706-128">`CreateMAlloc` Gibt ein-Objekt zurück, das der CLR ermöglicht, Zuordnungs Anforderungen über den Host zu senden, statt die Win32-Standardfunktionen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed706-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed706-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ed706-129">Requirements</span></span>  

 <span data-ttu-id="ed706-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed706-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed706-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ed706-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed706-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ed706-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed706-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed706-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed706-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed706-134">See also</span></span>

- [<span data-ttu-id="ed706-135">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed706-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="ed706-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed706-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
