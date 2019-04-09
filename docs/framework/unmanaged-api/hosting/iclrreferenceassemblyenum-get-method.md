---
title: ICLRReferenceAssemblyEnum::Get-Methode
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31d26ed6249bad8a7e2fbaab01264c1b32e1ff55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194473"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="94c6b-102">ICLRReferenceAssemblyEnum::Get-Methode</span><span class="sxs-lookup"><span data-stu-id="94c6b-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="94c6b-103">Ruft die Identität der Assembly am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="94c6b-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94c6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94c6b-104">Syntax</span></span>  
  
```  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94c6b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94c6b-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="94c6b-106">[in] Der nullbasierte Index, der die Identität der Assembly zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="94c6b-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="94c6b-107">[out] Ein Puffer mit der Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="94c6b-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="94c6b-108">[in, out] Die Größe der `pwzBuffer` Puffer.</span><span class="sxs-lookup"><span data-stu-id="94c6b-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94c6b-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="94c6b-109">Return Value</span></span>  
  
|<span data-ttu-id="94c6b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94c6b-110">HRESULT</span></span>|<span data-ttu-id="94c6b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94c6b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94c6b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="94c6b-112">S_OK</span></span>|`Get` <span data-ttu-id="94c6b-113">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94c6b-113">returned successfully.</span></span>|  
|<span data-ttu-id="94c6b-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="94c6b-114">ERROR_INSUFFICIENT_BUFFER</span></span>|`pwzBuffer` <span data-ttu-id="94c6b-115">ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="94c6b-115">is too small.</span></span>|  
|<span data-ttu-id="94c6b-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="94c6b-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="94c6b-117">Die Enumeration enthält keine Elemente mehr.</span><span class="sxs-lookup"><span data-stu-id="94c6b-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="94c6b-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94c6b-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94c6b-119">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="94c6b-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94c6b-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94c6b-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94c6b-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="94c6b-121">The call timed out.</span></span>|  
|<span data-ttu-id="94c6b-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94c6b-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94c6b-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="94c6b-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94c6b-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94c6b-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94c6b-125">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="94c6b-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94c6b-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94c6b-126">E_FAIL</span></span>|<span data-ttu-id="94c6b-127">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="94c6b-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94c6b-128">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="94c6b-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94c6b-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="94c6b-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94c6b-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94c6b-130">Remarks</span></span>  
 `Get` <span data-ttu-id="94c6b-131">wird in der Regel zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="94c6b-131">is typically called twice.</span></span> <span data-ttu-id="94c6b-132">Der erste Aufruf stellt einen null-Wert für `pwzBuffer`, und legt `pcchBufferSize` auf die Größe, die für die entsprechenden `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="94c6b-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="94c6b-133">Beim zweiten Aufruf wird ein geeigneter Größe `pwzBuffer`, und enthält Identitätsdaten kanonische Assembly Fertigstellung.</span><span class="sxs-lookup"><span data-stu-id="94c6b-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94c6b-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94c6b-134">Requirements</span></span>  
 <span data-ttu-id="94c6b-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94c6b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94c6b-136">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94c6b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94c6b-137">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="94c6b-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="94c6b-138">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="94c6b-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="94c6b-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94c6b-139">See also</span></span>

- [<span data-ttu-id="94c6b-140">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94c6b-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="94c6b-141">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94c6b-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
