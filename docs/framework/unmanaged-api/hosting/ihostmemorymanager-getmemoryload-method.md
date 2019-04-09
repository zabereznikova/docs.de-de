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
ms.openlocfilehash: c43fd1c63b14fc3254044247213bf09453da870e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175434"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="a39c8-102">IHostMemoryManager::GetMemoryLoad-Methode</span><span class="sxs-lookup"><span data-stu-id="a39c8-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="a39c8-103">Ruft die Menge des physischen Arbeitsspeichers, die derzeit verwendet wird und daher nicht verfügbar ist, durch den Host gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="a39c8-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a39c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a39c8-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a39c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a39c8-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="a39c8-106">[out] Ein Zeiger auf den ungefähren Prozentsatz des beanspruchten physikalischen Speichers, der zurzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a39c8-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="a39c8-107">[out] Ein Zeiger auf die Anzahl der Bytes, die die common Language Runtime (CLR) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a39c8-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a39c8-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a39c8-108">Return Value</span></span>  
  
|<span data-ttu-id="a39c8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a39c8-109">HRESULT</span></span>|<span data-ttu-id="a39c8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a39c8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a39c8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a39c8-111">S_OK</span></span>|`GetMemoryLoad` <span data-ttu-id="a39c8-112">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a39c8-112">returned successfully.</span></span>|  
|<span data-ttu-id="a39c8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a39c8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a39c8-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a39c8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a39c8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a39c8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a39c8-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a39c8-116">The call timed out.</span></span>|  
|<span data-ttu-id="a39c8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a39c8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a39c8-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a39c8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a39c8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a39c8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a39c8-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a39c8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a39c8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a39c8-121">E_FAIL</span></span>|<span data-ttu-id="a39c8-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a39c8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a39c8-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a39c8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a39c8-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a39c8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a39c8-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a39c8-125">Remarks</span></span>  
 `GetMemoryLoad` <span data-ttu-id="a39c8-126">Dient als Wrapper für Win32 `GlobalMemoryStatus` Funktion.</span><span class="sxs-lookup"><span data-stu-id="a39c8-126">wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="a39c8-127">Der Wert des `pMemoryLoad` entspricht der `dwMemoryLoad` im Feld der `MEMORYSTATUS` aus zurückgegebene Struktur `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="a39c8-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="a39c8-128">Die Laufzeit verwendet den zurückgegebenen Wert als eine Heuristik, für den Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="a39c8-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="a39c8-129">Z. B. wenn der Host meldet, dass der Großteil des Arbeitsspeichers verwendet wird, kann der Garbage Collector festlegen, ob Erfassen von mehrere Generationen, die die Menge an Arbeitsspeicher zu erhöhen, die möglicherweise verfügbar gemacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="a39c8-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a39c8-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a39c8-130">Requirements</span></span>  
 <span data-ttu-id="a39c8-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a39c8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a39c8-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a39c8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a39c8-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a39c8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a39c8-134">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a39c8-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a39c8-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a39c8-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="a39c8-136">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a39c8-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
