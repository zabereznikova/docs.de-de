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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176278"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="a3f6c-102">IHostMemoryManager::GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="a3f6c-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="a3f6c-103">Ruft den physischen Speicher ab, der derzeit verwendet wird und daher nicht verfügbar ist, wie vom Host gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3f6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3f6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3f6c-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="a3f6c-106">[out] Ein Zeiger auf den ungefähren Prozentsatz des gesamten physischen Speichers, der derzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="a3f6c-107">[out] Ein Zeiger auf die Anzahl der Bytes, die für die Common Language Runtime (CLR) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3f6c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3f6c-108">Return Value</span></span>  
  
|<span data-ttu-id="a3f6c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3f6c-109">HRESULT</span></span>|<span data-ttu-id="a3f6c-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3f6c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3f6c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3f6c-111">S_OK</span></span>|<span data-ttu-id="a3f6c-112">`GetMemoryLoad`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="a3f6c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3f6c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3f6c-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a3f6c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a3f6c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a3f6c-116">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-116">The call timed out.</span></span>|  
|<span data-ttu-id="a3f6c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a3f6c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a3f6c-118">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a3f6c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a3f6c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a3f6c-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a3f6c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3f6c-121">E_FAIL</span></span>|<span data-ttu-id="a3f6c-122">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a3f6c-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a3f6c-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3f6c-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a3f6c-125">Remarks</span></span>  
 <span data-ttu-id="a3f6c-126">`GetMemoryLoad`umschließt die Win32-Funktion. `GlobalMemoryStatus`</span><span class="sxs-lookup"><span data-stu-id="a3f6c-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="a3f6c-127">Der Wert `pMemoryLoad` von ist `dwMemoryLoad` das Äquivalent `MEMORYSTATUS` des `GlobalMemoryStatus`Felds in der Struktur, die von zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="a3f6c-128">Die Laufzeit verwendet den Rückgabewert als Heuristik für den Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="a3f6c-129">Wenn der Host beispielsweise meldet, dass der Großteil des Speichers verwendet wird, kann der Garbage Collector aus mehreren Generationen sammeln, um die Speichermenge zu erhöhen, die möglicherweise verfügbar werden kann.</span><span class="sxs-lookup"><span data-stu-id="a3f6c-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f6c-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a3f6c-130">Requirements</span></span>  
 <span data-ttu-id="a3f6c-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f6c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f6c-132">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a3f6c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3f6c-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a3f6c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3f6c-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f6c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f6c-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3f6c-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="a3f6c-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3f6c-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
