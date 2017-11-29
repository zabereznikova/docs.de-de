---
title: ICLRErrorReportingManager::EndCustomDump-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager.EndCustomDump
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 059ab01d3cc05bac84bb1a4cd8fffc7fc259ed60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="7da83-102">ICLRErrorReportingManager::EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="7da83-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="7da83-103">Entfernt die Konfiguration des benutzerdefinierten Stapeldumps, die in einen früheren Aufruf angegeben wurde die [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7da83-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7da83-104">Syntax</span></span>  
  
```  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7da83-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7da83-105">Return Value</span></span>  
  
|<span data-ttu-id="7da83-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7da83-106">HRESULT</span></span>|<span data-ttu-id="7da83-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7da83-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7da83-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7da83-108">S_OK</span></span>|<span data-ttu-id="7da83-109">`EndCustomDump`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7da83-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="7da83-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="7da83-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7da83-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7da83-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7da83-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7da83-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7da83-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7da83-113">The call timed out.</span></span>|  
|<span data-ttu-id="7da83-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7da83-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7da83-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7da83-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7da83-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7da83-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7da83-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7da83-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7da83-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7da83-118">E_FAIL</span></span>|<span data-ttu-id="7da83-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7da83-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7da83-120">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7da83-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7da83-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7da83-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7da83-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7da83-122">Remarks</span></span>  
 <span data-ttu-id="7da83-123">Die `EndCustomDump` Methode löscht die benutzerdefinierte Stapeldumpkonfiguration durch einen früheren Aufruf zum Festlegen der `BeginCustomDump` Methode und alle zugehörigen Status freigegeben.</span><span class="sxs-lookup"><span data-stu-id="7da83-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="7da83-124">Es sollte aufgerufen werden, nachdem die benutzerdefinierte Stapeldumps abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7da83-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7da83-125">Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.</span><span class="sxs-lookup"><span data-stu-id="7da83-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7da83-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7da83-126">Requirements</span></span>  
 <span data-ttu-id="7da83-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7da83-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da83-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7da83-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7da83-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7da83-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7da83-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da83-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da83-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7da83-131">See Also</span></span>  
 [<span data-ttu-id="7da83-132">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="7da83-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 [<span data-ttu-id="7da83-133">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7da83-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)  
 [<span data-ttu-id="7da83-134">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7da83-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
