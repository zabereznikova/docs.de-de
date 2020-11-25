---
title: IHostMemoryManager::GetMemoryLoad-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 0611b82e22ec9d5d2cde2a7f46e65b5e25733610
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731357"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="721a9-102">IHostMemoryManager::GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="721a9-102">IHostMemoryManager::GetMemoryLoad Method</span></span>

<span data-ttu-id="721a9-103">Ruft die Menge des physischen Speichers ab, der zurzeit verwendet wird und daher nicht verfügbar ist, wie vom Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="721a9-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="721a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="721a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="721a9-105">Parameters</span></span>  

 `pMemoryLoad`  
 <span data-ttu-id="721a9-106">vorgenommen Ein Zeiger auf den ungefähren Prozentsatz des gesamten physischen Speichers, der zurzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="721a9-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="721a9-107">vorgenommen Ein Zeiger auf die Anzahl der Bytes, die für die Common Language Runtime (CLR) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="721a9-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="721a9-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="721a9-108">Return Value</span></span>  
  
|<span data-ttu-id="721a9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="721a9-109">HRESULT</span></span>|<span data-ttu-id="721a9-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="721a9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="721a9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="721a9-111">S_OK</span></span>|<span data-ttu-id="721a9-112">`GetMemoryLoad` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="721a9-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="721a9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="721a9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="721a9-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="721a9-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="721a9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="721a9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="721a9-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="721a9-116">The call timed out.</span></span>|  
|<span data-ttu-id="721a9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="721a9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="721a9-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="721a9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="721a9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="721a9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="721a9-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="721a9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="721a9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="721a9-121">E_FAIL</span></span>|<span data-ttu-id="721a9-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="721a9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="721a9-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="721a9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="721a9-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="721a9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="721a9-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="721a9-125">Remarks</span></span>  

 <span data-ttu-id="721a9-126">`GetMemoryLoad` umschließt die Win32- `GlobalMemoryStatus` Funktion.</span><span class="sxs-lookup"><span data-stu-id="721a9-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="721a9-127">Der Wert von `pMemoryLoad` ist die Entsprechung des- `dwMemoryLoad` Felds in der-Struktur, die `MEMORYSTATUS` von zurückgegeben wird `GlobalMemoryStatus` .</span><span class="sxs-lookup"><span data-stu-id="721a9-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="721a9-128">Die Laufzeit verwendet den Rückgabewert als heuristisch für die Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="721a9-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="721a9-129">Wenn der Host z. b. meldet, dass der größte Teil des Arbeitsspeichers verwendet wird, kann der Garbage Collector die Erfassung aus mehreren Generierungen wählen, um die Menge an Arbeitsspeicher zu erhöhen, die potenziell verfügbar werden kann.</span><span class="sxs-lookup"><span data-stu-id="721a9-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="721a9-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="721a9-130">Requirements</span></span>  

 <span data-ttu-id="721a9-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="721a9-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="721a9-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="721a9-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="721a9-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="721a9-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="721a9-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="721a9-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="721a9-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="721a9-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="721a9-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="721a9-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
