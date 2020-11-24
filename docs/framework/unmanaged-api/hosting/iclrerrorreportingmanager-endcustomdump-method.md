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
ms.openlocfilehash: feaeba15fcc4e8264f7fde57d3b268a6b583ad83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677829"
---
# <a name="iclrerrorreportingmanagerendcustomdump-method"></a><span data-ttu-id="90e7d-102">ICLRErrorReportingManager::EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="90e7d-102">ICLRErrorReportingManager::EndCustomDump Method</span></span>

<span data-ttu-id="90e7d-103">Entfernt die benutzerdefinierte Stapel Sicherungs Konfiguration, die in einem früheren Aufrufen der [ICLRErrorReportingManager:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) -Methode angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="90e7d-103">Removes the custom stack dump configuration that was specified in an earlier call to the [ICLRErrorReportingManager::BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e7d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90e7d-104">Syntax</span></span>  
  
```cpp  
HRESULT EndCustomDump ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="90e7d-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="90e7d-105">Return Value</span></span>  
  
|<span data-ttu-id="90e7d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90e7d-106">HRESULT</span></span>|<span data-ttu-id="90e7d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="90e7d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90e7d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="90e7d-108">S_OK</span></span>|<span data-ttu-id="90e7d-109">`EndCustomDump` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90e7d-109">`EndCustomDump` returned successfully.</span></span>|  
|<span data-ttu-id="90e7d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="90e7d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="90e7d-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="90e7d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="90e7d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="90e7d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="90e7d-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="90e7d-113">The call timed out.</span></span>|  
|<span data-ttu-id="90e7d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="90e7d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="90e7d-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="90e7d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="90e7d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="90e7d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="90e7d-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="90e7d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="90e7d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="90e7d-118">E_FAIL</span></span>|<span data-ttu-id="90e7d-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="90e7d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="90e7d-120">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="90e7d-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="90e7d-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="90e7d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90e7d-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90e7d-122">Remarks</span></span>  

 <span data-ttu-id="90e7d-123">Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapel Sicherungs Konfiguration, die durch einen früheren Aufrufe der-Methode festgelegt wurde, `BeginCustomDump` und gibt jeden zugeordneten Zustand frei</span><span class="sxs-lookup"><span data-stu-id="90e7d-123">The `EndCustomDump` method clears the custom stack dump configuration set by an earlier call to the `BeginCustomDump` method and frees any associated state.</span></span> <span data-ttu-id="90e7d-124">Er sollte nach Abschluss des benutzerdefinierten Stapel Abbilds aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="90e7d-124">It should be called after the custom stack dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="90e7d-125">Wenn Sie den Vorgang nicht aufzurufen, ist der `EndCustomDump` Speicherfehler</span><span class="sxs-lookup"><span data-stu-id="90e7d-125">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e7d-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="90e7d-126">Requirements</span></span>  

 <span data-ttu-id="90e7d-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90e7d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e7d-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="90e7d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90e7d-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="90e7d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90e7d-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e7d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e7d-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90e7d-131">See also</span></span>

- [<span data-ttu-id="90e7d-132">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="90e7d-132">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="90e7d-133">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="90e7d-133">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="90e7d-134">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90e7d-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
