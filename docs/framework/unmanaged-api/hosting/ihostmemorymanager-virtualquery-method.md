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
ms.openlocfilehash: 00ec0b92a9f7151ee9b831c85548c4f61d87af68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192037"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="787aa-102">IHostMemoryManager::VirtualQuery-Methode</span><span class="sxs-lookup"><span data-stu-id="787aa-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="787aa-103">Dient als logischer Wrapper für die entsprechende Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="787aa-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="787aa-104">Die Win32-Implementierung von `VirtualQuery` Ruft Informationen zu einem Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="787aa-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787aa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="787aa-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="787aa-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="787aa-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="787aa-107">in Ein Zeiger auf die Adresse im virtuellen Speicher, die abgefragt werden soll.</span><span class="sxs-lookup"><span data-stu-id="787aa-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="787aa-108">vorgenommen Ein Zeiger auf eine-Struktur, die Informationen über den angegebenen Speicherbereich enthält.</span><span class="sxs-lookup"><span data-stu-id="787aa-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="787aa-109">in Die Größe (in Bytes) des Puffers, auf den `lpBuffer` zeigt.</span><span class="sxs-lookup"><span data-stu-id="787aa-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="787aa-110">vorgenommen Ein Zeiger auf die Anzahl der vom Informations Puffer zurückgegebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="787aa-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="787aa-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="787aa-111">Return Value</span></span>  
  
|<span data-ttu-id="787aa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="787aa-112">HRESULT</span></span>|<span data-ttu-id="787aa-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="787aa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="787aa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="787aa-114">S_OK</span></span>|<span data-ttu-id="787aa-115">`VirtualQuery` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="787aa-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="787aa-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="787aa-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="787aa-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="787aa-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="787aa-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="787aa-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="787aa-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="787aa-119">The call timed out.</span></span>|  
|<span data-ttu-id="787aa-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="787aa-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="787aa-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="787aa-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="787aa-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="787aa-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="787aa-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="787aa-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="787aa-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="787aa-124">E_FAIL</span></span>|<span data-ttu-id="787aa-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="787aa-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="787aa-126">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="787aa-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="787aa-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="787aa-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="787aa-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="787aa-128">Remarks</span></span>  
 <span data-ttu-id="787aa-129">`VirtualQuery` stellt Informationen zu einem Bereich von Seiten im virtuellen Adressraum des aufrufenden Prozesses bereit.</span><span class="sxs-lookup"><span data-stu-id="787aa-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="787aa-130">Mit dieser Implementierung wird der Wert des `pResult`-Parameters auf die Anzahl der im Informations Puffer zurückgegebenen Bytes festgelegt, und es wird ein HRESULT-Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="787aa-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="787aa-131">In der Win32-`VirtualQuery` Funktion ist der Rückgabewert die Puffergröße.</span><span class="sxs-lookup"><span data-stu-id="787aa-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="787aa-132">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="787aa-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="787aa-133">Die Implementierung von `VirtualQuery` des Betriebssystems verursacht keinen Deadlock und kann mit zufälligen Threads abgeschlossen werden, die im Benutzercode angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="787aa-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="787aa-134">Gehen Sie bei der Implementierung einer gehosteten Version dieser Methode sehr vorsichtig vor.</span><span class="sxs-lookup"><span data-stu-id="787aa-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="787aa-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="787aa-135">Requirements</span></span>  
 <span data-ttu-id="787aa-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="787aa-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="787aa-137">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="787aa-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="787aa-138">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="787aa-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="787aa-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="787aa-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787aa-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="787aa-140">See also</span></span>

- [<span data-ttu-id="787aa-141">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="787aa-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
