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
ms.openlocfilehash: a262ab26c9bbb93e42a11217fbeea6b3c55c7eb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966268"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="8162b-102">ICLRErrorReportingManager::EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="8162b-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>
<span data-ttu-id="8162b-103">Entfernt die benutzerdefinierte Stapel Sicherungs Konfiguration, die in einem früheren Aufrufen der [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) -Methode angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8162b-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8162b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8162b-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8162b-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8162b-105">Return Value</span></span>  
  
|<span data-ttu-id="8162b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8162b-106">HRESULT</span></span>|<span data-ttu-id="8162b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8162b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8162b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8162b-108">S_OK</span></span>|<span data-ttu-id="8162b-109">`EndCustomDump`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8162b-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="8162b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8162b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8162b-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8162b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8162b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8162b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8162b-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8162b-113">The call timed out.</span></span>|  
|<span data-ttu-id="8162b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8162b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8162b-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8162b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8162b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8162b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8162b-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8162b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8162b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8162b-118">E_FAIL</span></span>|<span data-ttu-id="8162b-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8162b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8162b-120">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8162b-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8162b-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8162b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8162b-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8162b-122">Remarks</span></span>  
 <span data-ttu-id="8162b-123">Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapel Sicherungs Konfiguration, die durch einen früheren `BeginCustomDump` Aufrufe der-Methode festgelegt wurde, und gibt jeden zugeordneten Zustand frei</span><span class="sxs-lookup"><span data-stu-id="8162b-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="8162b-124">Er sollte nach Abschluss des benutzerdefinierten Stapel Abbilds aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8162b-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8162b-125">Wenn Sie den `EndCustomDump` Vorgang nicht aufzurufen, ist der Speicherfehler</span><span class="sxs-lookup"><span data-stu-id="8162b-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8162b-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8162b-126">Requirements</span></span>  
 <span data-ttu-id="8162b-127">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8162b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8162b-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8162b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8162b-129">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8162b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8162b-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8162b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8162b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8162b-131">See also</span></span>

- [<span data-ttu-id="8162b-132">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="8162b-132">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="8162b-133">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8162b-133">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="8162b-134">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8162b-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
