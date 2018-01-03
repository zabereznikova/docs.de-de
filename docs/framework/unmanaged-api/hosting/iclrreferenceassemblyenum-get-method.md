---
title: ICLRReferenceAssemblyEnum::Get-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRReferenceAssemblyEnum.Get
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3cdf6a8eb761367d23e1ce61cd24727e7a3d6ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="b4d23-102">ICLRReferenceAssemblyEnum::Get-Methode</span><span class="sxs-lookup"><span data-stu-id="b4d23-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="b4d23-103">Ruft die Identität der Assembly am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="b4d23-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4d23-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4d23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4d23-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="b4d23-106">[in] Der nullbasierte Index des zurückzugebenden die Identität der Assembly.</span><span class="sxs-lookup"><span data-stu-id="b4d23-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="b4d23-107">[out] Ein Puffer mit Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="b4d23-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="b4d23-108">[in, out] Die Größe der `pwzBuffer` Puffer.</span><span class="sxs-lookup"><span data-stu-id="b4d23-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4d23-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4d23-109">Return Value</span></span>  
  
|<span data-ttu-id="b4d23-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4d23-110">HRESULT</span></span>|<span data-ttu-id="b4d23-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4d23-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4d23-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4d23-112">S_OK</span></span>|<span data-ttu-id="b4d23-113">`Get`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4d23-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="b4d23-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b4d23-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b4d23-115">`pwzBuffer`ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="b4d23-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="b4d23-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="b4d23-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="b4d23-117">Die Enumeration enthält keine Elemente mehr.</span><span class="sxs-lookup"><span data-stu-id="b4d23-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="b4d23-118">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="b4d23-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4d23-119">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b4d23-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4d23-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4d23-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4d23-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b4d23-121">The call timed out.</span></span>|  
|<span data-ttu-id="b4d23-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4d23-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4d23-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b4d23-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4d23-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4d23-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4d23-125">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="b4d23-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4d23-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4d23-126">E_FAIL</span></span>|<span data-ttu-id="b4d23-127">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b4d23-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4d23-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b4d23-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4d23-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b4d23-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4d23-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4d23-130">Remarks</span></span>  
 <span data-ttu-id="b4d23-131">`Get`wird in der Regel zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b4d23-131">`Get` is typically called twice.</span></span> <span data-ttu-id="b4d23-132">Der erste Aufruf stellt einen null-Wert für `pwzBuffer`, und legt `pcchBufferSize` auf die Größe, die für die entsprechenden `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="b4d23-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="b4d23-133">Beim zweiten Aufruf ein entsprechend skalierten `pwzBuffer`, und enthält Identitätsdaten kanonische Assembly nach dem Abschluss.</span><span class="sxs-lookup"><span data-stu-id="b4d23-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4d23-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4d23-134">Requirements</span></span>  
 <span data-ttu-id="b4d23-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4d23-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d23-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4d23-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4d23-137">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b4d23-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4d23-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4d23-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d23-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4d23-139">See Also</span></span>  
 [<span data-ttu-id="b4d23-140">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4d23-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="b4d23-141">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4d23-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
