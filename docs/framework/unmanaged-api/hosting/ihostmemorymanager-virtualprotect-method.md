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
ms.openlocfilehash: 473a52b55f793abc76883b0a5cd5b2a04756d9f7
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804358"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="48fcb-102">IHostMemoryManager::VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="48fcb-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="48fcb-103">Dient als logischer Wrapper für die entsprechende Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="48fcb-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="48fcb-104">Die Win32-Implementierung von `VirtualProtect` ändert den Schutz für einen Bereich von zugegebenen Seiten im virtuellen Adressraum des aufrufenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="48fcb-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48fcb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="48fcb-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48fcb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="48fcb-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="48fcb-107">in Ein Zeiger auf die Basisadresse des virtuellen Speichers, dessen Schutz Attribute geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="48fcb-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="48fcb-108">in Die Größe (in Bytes) des zu ändernden Bereichs von Speicherseiten.</span><span class="sxs-lookup"><span data-stu-id="48fcb-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="48fcb-109">in Der Typ des Speicher Schutzes, der angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="48fcb-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="48fcb-110">vorgenommen Ein Zeiger auf den vorherigen Wert des Speicher Schutzes.</span><span class="sxs-lookup"><span data-stu-id="48fcb-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48fcb-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48fcb-111">Return Value</span></span>  
  
|<span data-ttu-id="48fcb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48fcb-112">HRESULT</span></span>|<span data-ttu-id="48fcb-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="48fcb-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48fcb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="48fcb-114">S_OK</span></span>|<span data-ttu-id="48fcb-115">`VirtualProtect`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48fcb-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="48fcb-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48fcb-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48fcb-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="48fcb-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48fcb-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48fcb-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48fcb-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="48fcb-119">The call timed out.</span></span>|  
|<span data-ttu-id="48fcb-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48fcb-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48fcb-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="48fcb-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48fcb-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48fcb-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48fcb-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="48fcb-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48fcb-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48fcb-124">E_FAIL</span></span>|<span data-ttu-id="48fcb-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48fcb-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48fcb-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="48fcb-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48fcb-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="48fcb-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48fcb-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48fcb-128">Remarks</span></span>  
 <span data-ttu-id="48fcb-129">Diese Implementierung von `VirtualProtect` gibt einen HRESULT-Wert zurück, während die Win32-Implementierung einen Wert ungleich 0 (null) zurückgibt, um den Erfolg anzugeben, und einen Nullwert, um einen Fehler anzugeben.</span><span class="sxs-lookup"><span data-stu-id="48fcb-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="48fcb-130">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="48fcb-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48fcb-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48fcb-131">Requirements</span></span>  
 <span data-ttu-id="48fcb-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48fcb-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48fcb-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="48fcb-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48fcb-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48fcb-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48fcb-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48fcb-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48fcb-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48fcb-136">See also</span></span>

- [<span data-ttu-id="48fcb-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48fcb-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
