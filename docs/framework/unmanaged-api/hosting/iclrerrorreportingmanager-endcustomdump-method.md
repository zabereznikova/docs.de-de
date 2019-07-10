---
title: ICLRErrorReportingManager::EndCustomDump-Methode
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.EndCustomDump
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::EndCustomDump
helpviewer_keywords:
- ICLRErrorReportingManager::EndCustomDump method [.NET Framework hosting]
- EndCustomDump method [.NET Framework hosting]
ms.assetid: 88a5da04-8729-4108-82c4-af206a7d483e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c2d2e5454a26111748f9676cfe1ce5caa76cad5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772841"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="9854a-102">ICLRErrorReportingManager::EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="9854a-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="9854a-103">Entfernt die Konfiguration des benutzerdefinierten Stapeldumps, die in einem früheren Aufruf angegeben wurde der [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9854a-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9854a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9854a-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9854a-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9854a-105">Return Value</span></span>  
  
|<span data-ttu-id="9854a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9854a-106">HRESULT</span></span>|<span data-ttu-id="9854a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9854a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9854a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9854a-108">S_OK</span></span>|<span data-ttu-id="9854a-109">`EndCustomDump` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9854a-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="9854a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9854a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9854a-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9854a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9854a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9854a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9854a-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9854a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9854a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9854a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9854a-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9854a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9854a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9854a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9854a-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9854a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9854a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9854a-118">E_FAIL</span></span>|<span data-ttu-id="9854a-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9854a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9854a-120">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9854a-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9854a-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9854a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9854a-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9854a-122">Remarks</span></span>  
 <span data-ttu-id="9854a-123">Die `EndCustomDump` Methode löscht die benutzerdefinierte Stapeldumpkonfiguration durch einen früheren Aufruf zum Festlegen der `BeginCustomDump` Methode und alle zugeordneten Zustand freigibt.</span><span class="sxs-lookup"><span data-stu-id="9854a-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="9854a-124">Es sollte aufgerufen werden, nachdem die benutzerdefinierte Stapelabbild abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9854a-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9854a-125">Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.</span><span class="sxs-lookup"><span data-stu-id="9854a-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9854a-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9854a-126">Requirements</span></span>  
 <span data-ttu-id="9854a-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9854a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9854a-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9854a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9854a-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9854a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9854a-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9854a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9854a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9854a-131">See also</span></span>

- [<span data-ttu-id="9854a-132">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="9854a-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="9854a-133">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9854a-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="9854a-134">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9854a-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
