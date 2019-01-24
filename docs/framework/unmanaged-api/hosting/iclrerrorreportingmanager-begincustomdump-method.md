---
title: ICLRErrorReportingManager::BeginCustomDump-Methode
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.BeginCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e6d3f4a1c77e8b5070086e871d4d08fcf138f6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696924"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="15688-102">ICLRErrorReportingManager::BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="15688-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="15688-103">Gibt die Konfiguration von benutzerdefinierten Heap-Speicherabbildern für die Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="15688-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15688-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15688-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15688-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15688-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="15688-106">[in] Ein [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) Wert, der die Art des auf dem das benutzerdefinierte Heap-Speicherabbild erstellen angibt.</span><span class="sxs-lookup"><span data-stu-id="15688-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="15688-107">[in] Die Länge der `items` Array.</span><span class="sxs-lookup"><span data-stu-id="15688-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="15688-108">Wenn `dwFlavor` ist kein DUMP_FLAVOR_Mini, `dwNumItems` sollte Null sein.</span><span class="sxs-lookup"><span data-stu-id="15688-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="15688-109">[in] Ein Array von [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) -Instanzen, die für die hinzuzufügenden Minidump Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="15688-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="15688-110">Wenn `dwFlavor` ist kein DUMP_FLAVOR_Mini, `items` sollte null sein.</span><span class="sxs-lookup"><span data-stu-id="15688-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="15688-111">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="15688-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15688-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15688-112">Return Value</span></span>  
  
|<span data-ttu-id="15688-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15688-113">HRESULT</span></span>|<span data-ttu-id="15688-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15688-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15688-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="15688-115">S_OK</span></span>|<span data-ttu-id="15688-116">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="15688-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="15688-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15688-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15688-118">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="15688-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15688-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15688-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15688-120">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="15688-120">The call timed out.</span></span>|  
|<span data-ttu-id="15688-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15688-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15688-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="15688-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15688-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15688-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15688-124">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="15688-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15688-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15688-125">E_FAIL</span></span>|<span data-ttu-id="15688-126">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="15688-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15688-127">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="15688-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15688-128">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="15688-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15688-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15688-129">Remarks</span></span>  
 <span data-ttu-id="15688-130">Die `BeginCustomDump` Methode legt die benutzerdefinierte Konfiguration von Heapdumps fest.</span><span class="sxs-lookup"><span data-stu-id="15688-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="15688-131">Die [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) Methode löscht die Konfiguration des benutzerdefinierten Heap-Speicherabbild und alle zugeordneten Zustand freigibt.</span><span class="sxs-lookup"><span data-stu-id="15688-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="15688-132">Es sollte aufgerufen werden, nachdem das benutzerdefinierte Heap-Speicherabbild abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="15688-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15688-133">Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.</span><span class="sxs-lookup"><span data-stu-id="15688-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15688-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15688-134">Requirements</span></span>  
 <span data-ttu-id="15688-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15688-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15688-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15688-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15688-137">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15688-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15688-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15688-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15688-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15688-139">See also</span></span>
- [<span data-ttu-id="15688-140">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="15688-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="15688-141">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="15688-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="15688-142">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15688-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
