---
title: IHostMemoryManager::VirtualProtect-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62aa6b1d9be86a9b60abf894d67555f706e6a8ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139905"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="6c5d8-102">IHostMemoryManager::VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="6c5d8-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="6c5d8-103">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="6c5d8-104">Die Win32-Implementierung von `VirtualProtect` ändert den Schutz in einem Bereich der Seiten im virtuellen Adressraum des aufrufenden Prozesses, die ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c5d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6c5d8-105">Syntax</span></span>  
  
```  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c5d8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6c5d8-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="6c5d8-107">[in] Ein Zeiger auf die Basisadresse des virtuellen Speichers, deren Schutzattribute sind geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="6c5d8-108">[in] Die Größe in Bytes des Bereichs der Seiten im Arbeitsspeicher geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="6c5d8-109">[in] Der Typ des Speicherschutzes angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="6c5d8-110">[out] Ein Zeiger auf den Wert des vorherigen Arbeitsspeichers Schutz.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c5d8-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6c5d8-111">Return Value</span></span>  
  
|<span data-ttu-id="6c5d8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c5d8-112">HRESULT</span></span>|<span data-ttu-id="6c5d8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c5d8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c5d8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c5d8-114">S_OK</span></span>|`VirtualProtect` <span data-ttu-id="6c5d8-115">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-115">returned successfully.</span></span>|  
|<span data-ttu-id="6c5d8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c5d8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c5d8-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6c5d8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6c5d8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6c5d8-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-119">The call timed out.</span></span>|  
|<span data-ttu-id="6c5d8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6c5d8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6c5d8-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6c5d8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6c5d8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6c5d8-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6c5d8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c5d8-124">E_FAIL</span></span>|<span data-ttu-id="6c5d8-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6c5d8-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6c5d8-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c5d8-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6c5d8-128">Remarks</span></span>  
 <span data-ttu-id="6c5d8-129">Diese Implementierung der `VirtualProtect` einen HRESULT-Wert, während die Win32-Implementierung einen Wert ungleich Null zum Erfolg zurückgibt und einen Nullwert, während ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="6c5d8-130">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="6c5d8-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c5d8-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6c5d8-131">Requirements</span></span>  
 <span data-ttu-id="6c5d8-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c5d8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c5d8-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c5d8-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c5d8-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6c5d8-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6c5d8-135">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6c5d8-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6c5d8-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c5d8-136">See also</span></span>

- [<span data-ttu-id="6c5d8-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6c5d8-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
