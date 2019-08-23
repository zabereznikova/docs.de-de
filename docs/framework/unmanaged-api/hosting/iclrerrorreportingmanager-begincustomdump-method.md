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
ms.openlocfilehash: 98eebd489792f57f7f98d3596d4f25be2e847441
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966279"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="0c3e0-102">ICLRErrorReportingManager::BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="0c3e0-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="0c3e0-103">Gibt die Konfiguration von benutzerdefinierten Heap-Abbilder für die Fehlerberichterstattung an.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c3e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c3e0-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c3e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c3e0-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="0c3e0-106">in Ein [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) -Wert, der die Art des Heap Abbilds angibt, auf dem der benutzerdefinierte Heap Abbild erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-106">[in] A [ECustomDumpFlavor](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="0c3e0-107">in Die Länge des `items` Arrays.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="0c3e0-108">Wenn `dwFlavor` nicht DUMP_FLAVOR_Mini ist, `dwNumItems` sollte 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="0c3e0-109">in Ein Array von [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) -Instanzen, das die Elemente angibt, die dem Mini Abbild hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-109">[in] An array of [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="0c3e0-110">Wenn `dwFlavor` nicht DUMP_FLAVOR_Mini ist, `items` sollte NULL sein.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="0c3e0-111">in Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c3e0-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0c3e0-112">Return Value</span></span>  
  
|<span data-ttu-id="0c3e0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c3e0-113">HRESULT</span></span>|<span data-ttu-id="0c3e0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c3e0-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c3e0-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c3e0-115">S_OK</span></span>|<span data-ttu-id="0c3e0-116">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="0c3e0-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c3e0-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c3e0-118">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c3e0-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c3e0-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c3e0-120">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-120">The call timed out.</span></span>|  
|<span data-ttu-id="0c3e0-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c3e0-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c3e0-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c3e0-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c3e0-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c3e0-124">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c3e0-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c3e0-125">E_FAIL</span></span>|<span data-ttu-id="0c3e0-126">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c3e0-127">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c3e0-128">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c3e0-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c3e0-129">Remarks</span></span>  
 <span data-ttu-id="0c3e0-130">Die `BeginCustomDump` -Methode legt die benutzerdefinierte Heap Speicherkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="0c3e0-131">Die [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) -Methode löscht die benutzerdefinierte Heap Speicherkonfiguration und gibt jeden zugeordneten Zustand frei.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-131">The [EndCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="0c3e0-132">Er sollte nach Abschluss des benutzerdefinierten Heap Abbilds aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0c3e0-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0c3e0-133">Wenn Sie den `EndCustomDump` Vorgang nicht aufzurufen, ist der Speicherfehler</span><span class="sxs-lookup"><span data-stu-id="0c3e0-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c3e0-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c3e0-134">Requirements</span></span>  
 <span data-ttu-id="0c3e0-135">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c3e0-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c3e0-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c3e0-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c3e0-137">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0c3e0-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c3e0-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c3e0-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3e0-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c3e0-139">See also</span></span>

- [<span data-ttu-id="0c3e0-140">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="0c3e0-140">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)
- [<span data-ttu-id="0c3e0-141">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0c3e0-141">ECustomDumpFlavor Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="0c3e0-142">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c3e0-142">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
