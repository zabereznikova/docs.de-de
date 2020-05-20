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
ms.openlocfilehash: 4c83ffaf920abe005ba987e0a744e13aa0d3c016
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615669"
---
# <a name="iclrerrorreportingmanagerbegincustomdump-method"></a><span data-ttu-id="a9bc3-102">ICLRErrorReportingManager::BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="a9bc3-102">ICLRErrorReportingManager::BeginCustomDump Method</span></span>
<span data-ttu-id="a9bc3-103">Gibt die Konfiguration von benutzerdefinierten Heap-Abbilder für die Fehlerberichterstattung an.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-103">Specifies the configuration of custom heap dumps for error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9bc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9bc3-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginCustomDump (  
    [in] ECustomDumpFlavor dwFlavor,  
    [in] DWORD dwNumItems,  
    [in, size_is(dwNumItems), length_is(dwNumItems)] CustomDumpItem items[],  
    DWORD dwReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9bc3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9bc3-105">Parameters</span></span>  
 `dwFlavor`  
 <span data-ttu-id="a9bc3-106">in Ein [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) -Wert, der die Art des Heap Abbilds angibt, auf dem der benutzerdefinierte Heap Abbild erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-106">[in] A [ECustomDumpFlavor](ecustomdumpflavor-enumeration.md) value that indicates the kind of heap dump upon which to build the custom heap dump.</span></span>  
  
 `dwNumItems`  
 <span data-ttu-id="a9bc3-107">in Die Länge des `items` Arrays.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-107">[in] The length of the `items` array.</span></span> <span data-ttu-id="a9bc3-108">Wenn `dwFlavor` nicht DUMP_FLAVOR_Mini ist, `dwNumItems` sollte 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-108">If `dwFlavor` is not DUMP_FLAVOR_Mini, `dwNumItems` should be zero.</span></span>  
  
 `items`  
 <span data-ttu-id="a9bc3-109">in Ein Array von [CustomDumpItem](customdumpitem-structure.md) -Instanzen, das die Elemente angibt, die dem Mini Abbild hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-109">[in] An array of [CustomDumpItem](customdumpitem-structure.md) instances, specifying the items to add to the mini-dump.</span></span> <span data-ttu-id="a9bc3-110">Wenn `dwFlavor` nicht DUMP_FLAVOR_Mini ist, `items` sollte NULL sein.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-110">If `dwFlavor` is not DUMP_FLAVOR_Mini, `items` should be null.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="a9bc3-111">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-111">[in] Reserved for future use.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9bc3-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a9bc3-112">Return Value</span></span>  
  
|<span data-ttu-id="a9bc3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9bc3-113">HRESULT</span></span>|<span data-ttu-id="a9bc3-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a9bc3-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9bc3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9bc3-115">S_OK</span></span>|<span data-ttu-id="a9bc3-116">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="a9bc3-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9bc3-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9bc3-118">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9bc3-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9bc3-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9bc3-120">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-120">The call timed out.</span></span>|  
|<span data-ttu-id="a9bc3-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9bc3-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9bc3-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9bc3-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9bc3-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9bc3-124">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9bc3-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9bc3-125">E_FAIL</span></span>|<span data-ttu-id="a9bc3-126">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9bc3-127">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9bc3-128">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9bc3-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a9bc3-129">Remarks</span></span>  
 <span data-ttu-id="a9bc3-130">Die- `BeginCustomDump` Methode legt die benutzerdefinierte Heap Speicherkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-130">The `BeginCustomDump` method sets custom heap dump configuration.</span></span> <span data-ttu-id="a9bc3-131">Die [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) -Methode löscht die benutzerdefinierte Heap Speicherkonfiguration und gibt jeden zugeordneten Zustand frei.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-131">The [EndCustomDump](iclrerrorreportingmanager-endcustomdump-method.md) method clears the custom heap dump configuration and frees any associated state.</span></span> <span data-ttu-id="a9bc3-132">Er sollte nach Abschluss des benutzerdefinierten Heap Abbilds aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a9bc3-132">It should be called after the custom heap dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9bc3-133">Wenn Sie den Vorgang nicht aufzurufen, ist der `EndCustomDump` Speicherfehler</span><span class="sxs-lookup"><span data-stu-id="a9bc3-133">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9bc3-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9bc3-134">Requirements</span></span>  
 <span data-ttu-id="a9bc3-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9bc3-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9bc3-136">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a9bc3-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9bc3-137">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a9bc3-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9bc3-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9bc3-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bc3-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9bc3-139">See also</span></span>

- [<span data-ttu-id="a9bc3-140">CustomDumpItem-Struktur</span><span class="sxs-lookup"><span data-stu-id="a9bc3-140">CustomDumpItem Structure</span></span>](customdumpitem-structure.md)
- [<span data-ttu-id="a9bc3-141">ECustomDumpFlavor-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a9bc3-141">ECustomDumpFlavor Enumeration</span></span>](ecustomdumpflavor-enumeration.md)
- [<span data-ttu-id="a9bc3-142">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9bc3-142">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
