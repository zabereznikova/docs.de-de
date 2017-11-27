---
title: ICLRErrorReportingManager::BeginCustomDump-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.BeginCustomDump
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::BeginCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::BeginCustomDump method [.NET Framework hosting]
- BeginCustomDump method
ms.assetid: 93424a87-ba13-4fa1-b4dc-69d44437b7ae
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c90357f969b19c767d4bb45d4d3105f50cd5682a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="88ac1-102">ICLRErrorReportingManager::BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="88ac1-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="88ac1-103">Gibt die Konfiguration des benutzerdefinierten Heapdumps für die Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="88ac1-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88ac1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88ac1-104">Syntax</span></span>  
  
```  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88ac1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="88ac1-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="88ac1-106">[in] Ein [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) Wert, der den Typ des auf dem das Speicherabbild benutzerdefinierte Heap erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="88ac1-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="88ac1-107">[in] Die Länge der `items` Array.</span><span class="sxs-lookup"><span data-stu-id="88ac1-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="88ac1-108">Wenn `dwFlavor` ist kein DUMP_FLAVOR_Mini, `dwNumItems` sollte 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="88ac1-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="88ac1-109">[in] Ein Array von [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) Instanzen, die angeben, die die Elemente, die den Minidump hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="88ac1-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="88ac1-110">Wenn `dwFlavor` ist kein DUMP_FLAVOR_Mini, `items` sollte null sein.</span><span class="sxs-lookup"><span data-stu-id="88ac1-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="88ac1-111">[in] Für zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="88ac1-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88ac1-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="88ac1-112">Return Value</span></span>  
  
|<span data-ttu-id="88ac1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88ac1-113">HRESULT</span></span>|<span data-ttu-id="88ac1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88ac1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88ac1-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="88ac1-115">S_OK</span></span>|<span data-ttu-id="88ac1-116">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="88ac1-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="88ac1-117">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="88ac1-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="88ac1-118">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="88ac1-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="88ac1-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="88ac1-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="88ac1-120">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="88ac1-120">The call timed out.</span></span>|  
|<span data-ttu-id="88ac1-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="88ac1-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="88ac1-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="88ac1-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="88ac1-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="88ac1-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="88ac1-124">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="88ac1-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="88ac1-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88ac1-125">E_FAIL</span></span>|<span data-ttu-id="88ac1-126">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="88ac1-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88ac1-127">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="88ac1-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="88ac1-128">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="88ac1-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88ac1-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="88ac1-129">Remarks</span></span>  
 <span data-ttu-id="88ac1-130">Die `BeginCustomDump` -Methode fest benutzerdefinierten Heap Sicherungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="88ac1-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="88ac1-131">Die [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) Methode löscht die Sicherungskonfiguration für benutzerdefinierte Heap und alle zugeordneten Zustand freigibt.</span><span class="sxs-lookup"><span data-stu-id="88ac1-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="88ac1-132">Es sollte aufgerufen werden, nachdem das Speicherabbild benutzerdefinierte Heap abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="88ac1-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88ac1-133">Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.</span><span class="sxs-lookup"><span data-stu-id="88ac1-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88ac1-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88ac1-134">Requirements</span></span>  
 <span data-ttu-id="88ac1-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88ac1-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88ac1-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88ac1-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88ac1-137">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="88ac1-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88ac1-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88ac1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ac1-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88ac1-139">See Also</span></span>  
 [<span data-ttu-id="88ac1-140">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="88ac1-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="88ac1-141">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="88ac1-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="88ac1-142">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="88ac1-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
