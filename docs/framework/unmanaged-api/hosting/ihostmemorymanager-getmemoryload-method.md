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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92ef3a6d7eb45a3b978c916c406bfa6199f17d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440147"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="e3ebd-102">IHostMemoryManager::GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="e3ebd-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="e3ebd-103">Ruft die Größe des physischen Speichers, der zurzeit verwendet wird und daher nicht verfügbar ist, von dem Host gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ebd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3ebd-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3ebd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3ebd-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="e3ebd-106">[out] Ein Zeiger auf den ungefähren Prozentsatz des gesamten physischen Arbeitsspeichers, die derzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="e3ebd-107">[out] Ein Zeiger auf die Anzahl der Bytes, die für die common Language Runtime (CLR) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3ebd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e3ebd-108">Return Value</span></span>  
  
|<span data-ttu-id="e3ebd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3ebd-109">HRESULT</span></span>|<span data-ttu-id="e3ebd-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e3ebd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3ebd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3ebd-111">S_OK</span></span>|<span data-ttu-id="e3ebd-112">`GetMemoryLoad` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="e3ebd-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="e3ebd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3ebd-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3ebd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3ebd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3ebd-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-116">The call timed out.</span></span>|  
|<span data-ttu-id="e3ebd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3ebd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3ebd-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3ebd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3ebd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3ebd-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3ebd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3ebd-121">E_FAIL</span></span>|<span data-ttu-id="e3ebd-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3ebd-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3ebd-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3ebd-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3ebd-125">Remarks</span></span>  
 <span data-ttu-id="e3ebd-126">`GetMemoryLoad` Dient als Wrapper für Win32 `GlobalMemoryStatus` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="e3ebd-127">Den Wert der `pMemoryLoad` ist das Äquivalent der `dwMemoryLoad` -Feld in der `MEMORYSTATUS` Merry Struktur `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="e3ebd-128">Die Common Language Runtime verwendet den Rückgabewert als Heuristik für den Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="e3ebd-129">Wenn der Host meldet, dass die Mehrheit des Arbeitsspeichers verwendet wird, kann z. B. der Garbage Collector entscheiden, Erfassen von mehreren Generierungen, die die Menge an Arbeitsspeicher zu erhöhen, die potenziell verfügbar gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="e3ebd-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3ebd-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3ebd-130">Requirements</span></span>  
 <span data-ttu-id="e3ebd-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3ebd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3ebd-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3ebd-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3ebd-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e3ebd-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3ebd-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3ebd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ebd-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3ebd-135">See Also</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
 [<span data-ttu-id="e3ebd-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3ebd-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
