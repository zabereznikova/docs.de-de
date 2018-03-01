---
title: IHostMemoryManager::VirtualProtect-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77e8e163a16752934d0a1d826cc8463b3d3281bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="96a9a-102">IHostMemoryManager::VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="96a9a-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="96a9a-103">Dient als logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="96a9a-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="96a9a-104">Die Win32-Implementierung von `VirtualProtect` ändert den Schutz für einen Bereich der Seiten im virtuellen Adressraum des aufrufenden Prozesses, die ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="96a9a-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a9a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="96a9a-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96a9a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="96a9a-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="96a9a-107">[in] Ein Zeiger auf die Basisadresse des virtuellen Speichers, dessen Schutzattribute werden geändert werden.</span><span class="sxs-lookup"><span data-stu-id="96a9a-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="96a9a-108">[in] Die Größe in Bytes, des Bereichs der Seiten im Arbeitsspeicher geändert werden.</span><span class="sxs-lookup"><span data-stu-id="96a9a-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="96a9a-109">[in] Der Typ der Arbeitsspeicherschutz anwenden.</span><span class="sxs-lookup"><span data-stu-id="96a9a-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="96a9a-110">[out] Ein Zeiger auf den Wert des vorherigen Arbeitsspeichers Schutz.</span><span class="sxs-lookup"><span data-stu-id="96a9a-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96a9a-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="96a9a-111">Return Value</span></span>  
  
|<span data-ttu-id="96a9a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96a9a-112">HRESULT</span></span>|<span data-ttu-id="96a9a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96a9a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96a9a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="96a9a-114">S_OK</span></span>|<span data-ttu-id="96a9a-115">`VirtualProtect`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="96a9a-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="96a9a-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="96a9a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="96a9a-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="96a9a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="96a9a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96a9a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="96a9a-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="96a9a-119">The call timed out.</span></span>|  
|<span data-ttu-id="96a9a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="96a9a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="96a9a-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="96a9a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="96a9a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="96a9a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="96a9a-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="96a9a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="96a9a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96a9a-124">E_FAIL</span></span>|<span data-ttu-id="96a9a-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="96a9a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96a9a-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="96a9a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="96a9a-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="96a9a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96a9a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96a9a-128">Remarks</span></span>  
 <span data-ttu-id="96a9a-129">Diese Implementierung der `VirtualProtect` gibt einen HRESULT-Wert, während die Win32-Implementierung einen Wert ungleich 0 (null), um einen Erfolg zu melden zurückgibt und den Wert 0, um einen Fehler anzugeben.</span><span class="sxs-lookup"><span data-stu-id="96a9a-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="96a9a-130">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="96a9a-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96a9a-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96a9a-131">Requirements</span></span>  
 <span data-ttu-id="96a9a-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96a9a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96a9a-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96a9a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96a9a-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="96a9a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96a9a-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96a9a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a9a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96a9a-136">See Also</span></span>  
 [<span data-ttu-id="96a9a-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96a9a-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
