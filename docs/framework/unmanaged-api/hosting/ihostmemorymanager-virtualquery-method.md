---
title: IHostMemoryManager::VirtualQuery-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 885871f3e6b3f10bfb7d660e2d6889e243ef751b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734363"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="1b892-102">IHostMemoryManager::VirtualQuery-Methode</span><span class="sxs-lookup"><span data-stu-id="1b892-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="1b892-103">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="1b892-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="1b892-104">Die Win32-Implementierung von `VirtualQuery` Ruft Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="1b892-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b892-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b892-105">Syntax</span></span>  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b892-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b892-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="1b892-107">[in] Ein Zeiger auf die Adresse im virtuellen Speicher abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="1b892-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="1b892-108">[out] Ein Zeiger auf eine Struktur, die Informationen über den angegebenen Speicherbereich enthält.</span><span class="sxs-lookup"><span data-stu-id="1b892-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="1b892-109">[in] Die Größe des Puffers in Bytes, die `lpBuffer` verweist auf.</span><span class="sxs-lookup"><span data-stu-id="1b892-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="1b892-110">[out] Ein Zeiger auf die Anzahl der Bytes, die vom Informationspuffer zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b892-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b892-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b892-111">Return Value</span></span>  
  
|<span data-ttu-id="1b892-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b892-112">HRESULT</span></span>|<span data-ttu-id="1b892-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b892-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b892-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b892-114">S_OK</span></span>|<span data-ttu-id="1b892-115">`VirtualQuery` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b892-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="1b892-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b892-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b892-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1b892-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b892-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b892-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b892-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b892-119">The call timed out.</span></span>|  
|<span data-ttu-id="1b892-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b892-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b892-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1b892-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b892-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b892-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b892-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1b892-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b892-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b892-124">E_FAIL</span></span>|<span data-ttu-id="1b892-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b892-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b892-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b892-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b892-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1b892-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b892-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b892-128">Remarks</span></span>  
 <span data-ttu-id="1b892-129">`VirtualQuery` enthält Informationen über einen Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="1b892-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="1b892-130">Diese Implementierung legt den Wert für die `pResult` Parameter, um die Anzahl der Bytes im Informationspuffer zurückgegeben, und gibt einen HRESULT-Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="1b892-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="1b892-131">In der Win32- `VirtualQuery` -Funktion, der Rückgabewert ist die Größe des Puffers.</span><span class="sxs-lookup"><span data-stu-id="1b892-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="1b892-132">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="1b892-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b892-133">Implementierung des Betriebssystems `VirtualQuery` tritt kein Deadlock und kann mit zufällig im Benutzercode angehaltenen Threads bis zum Abschluss ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b892-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="1b892-134">Seien Sie äußerst vorsichtig, wenn Sie eine gehostete Version dieser Methode zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="1b892-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b892-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b892-135">Requirements</span></span>  
 <span data-ttu-id="1b892-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b892-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b892-137">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b892-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b892-138">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1b892-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b892-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b892-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b892-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b892-140">See also</span></span>
- [<span data-ttu-id="1b892-141">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b892-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
