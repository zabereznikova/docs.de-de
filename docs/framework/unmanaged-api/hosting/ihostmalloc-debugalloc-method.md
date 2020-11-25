---
title: IHostMAlloc::DebugAlloc-Methode
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 49de0398dd32970bd8ceb0fd24178e75df5d14b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713490"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="a47ba-102">IHostMAlloc::DebugAlloc-Methode</span><span class="sxs-lookup"><span data-stu-id="a47ba-102">IHostMAlloc::DebugAlloc Method</span></span>

<span data-ttu-id="a47ba-103">Fordert an, dass der Host die angegebene Arbeitsspeicher Menge aus dem Heap zuweist und zusätzlich nachverfolgt, wo der Arbeitsspeicher belegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a47ba-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a47ba-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a47ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a47ba-105">Parameters</span></span>  

 `cbSize`  
 <span data-ttu-id="a47ba-106">in Die Größe der aktuellen Speicher Belegungs Anforderung in Bytes.</span><span class="sxs-lookup"><span data-stu-id="a47ba-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="a47ba-107">in Einer der [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) -Werte, der die Auswirkung eines Zuordnungs Fehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="a47ba-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="a47ba-108">in Die Codedatei der ausführbaren Datei, die deentschlgt wird.</span><span class="sxs-lookup"><span data-stu-id="a47ba-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="a47ba-109">in Die Zeilennummer in, in der `pszFileName` die Zuordnung angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="a47ba-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="a47ba-110">vorgenommen Ein Zeiger auf den zugeordneten Arbeitsspeicher oder NULL, wenn die Anforderung nicht abgeschlossen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="a47ba-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a47ba-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a47ba-111">Return Value</span></span>  
  
|<span data-ttu-id="a47ba-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a47ba-112">HRESULT</span></span>|<span data-ttu-id="a47ba-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a47ba-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a47ba-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a47ba-114">S_OK</span></span>|<span data-ttu-id="a47ba-115">`DebugAlloc` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a47ba-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="a47ba-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a47ba-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a47ba-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a47ba-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a47ba-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a47ba-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a47ba-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a47ba-119">The call timed out.</span></span>|  
|<span data-ttu-id="a47ba-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a47ba-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a47ba-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a47ba-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a47ba-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a47ba-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a47ba-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a47ba-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a47ba-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a47ba-124">E_FAIL</span></span>|<span data-ttu-id="a47ba-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a47ba-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a47ba-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="a47ba-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a47ba-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a47ba-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a47ba-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a47ba-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a47ba-129">Zum Abschluss der Zuordnungs Anforderung war nicht genügend Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a47ba-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a47ba-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a47ba-130">Remarks</span></span>  

 <span data-ttu-id="a47ba-131">Die CLR ruft einen Schnittstellen Zeiger auf eine [IHostMAlloc](ihostmalloc-interface.md) -Instanz ab, indem die [IHostMemoryManager:: createmzuzugsmethode](ihostmemorymanager-createmalloc-method.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a47ba-131">The CLR gets an interface pointer to an [IHostMalloc](ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="a47ba-132">`DebugAlloc` ermöglicht der Laufzeit, Code Dateiinformationen für die Verwendung während des Debuggens zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a47ba-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a47ba-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a47ba-133">Requirements</span></span>  

 <span data-ttu-id="a47ba-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a47ba-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47ba-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a47ba-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a47ba-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a47ba-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a47ba-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a47ba-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47ba-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a47ba-138">See also</span></span>

- [<span data-ttu-id="a47ba-139">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ba-139">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="a47ba-140">IHostMalloc-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47ba-140">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
