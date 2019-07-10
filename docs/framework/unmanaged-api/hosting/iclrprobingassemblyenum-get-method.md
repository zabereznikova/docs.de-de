---
title: ICLRProbingAssemblyEnum::Get-Methode
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3225e42df44e719ecde31c26fae70f26731fa157
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761583"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="27ba4-102">ICLRProbingAssemblyEnum::Get-Methode</span><span class="sxs-lookup"><span data-stu-id="27ba4-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="27ba4-103">Ruft die Identität der Assembly am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="27ba4-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ba4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27ba4-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27ba4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27ba4-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="27ba4-106">[in] Der nullbasierte Index, der die Identität der Assembly zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="27ba4-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="27ba4-107">[out] Ein Puffer mit der Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="27ba4-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="27ba4-108">[in, out] Die Größe der `pwzBuffer` Puffer.</span><span class="sxs-lookup"><span data-stu-id="27ba4-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27ba4-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="27ba4-109">Return Value</span></span>  
  
|<span data-ttu-id="27ba4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27ba4-110">HRESULT</span></span>|<span data-ttu-id="27ba4-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27ba4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27ba4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="27ba4-112">S_OK</span></span>|<span data-ttu-id="27ba4-113">`Get` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27ba4-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="27ba4-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="27ba4-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="27ba4-115">`pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="27ba4-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="27ba4-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="27ba4-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="27ba4-117">Die Enumeration enthält keine Elemente mehr.</span><span class="sxs-lookup"><span data-stu-id="27ba4-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="27ba4-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27ba4-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27ba4-119">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="27ba4-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27ba4-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27ba4-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27ba4-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="27ba4-121">The call timed out.</span></span>|  
|<span data-ttu-id="27ba4-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27ba4-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27ba4-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="27ba4-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27ba4-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27ba4-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27ba4-125">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="27ba4-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27ba4-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27ba4-126">E_FAIL</span></span>|<span data-ttu-id="27ba4-127">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="27ba4-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27ba4-128">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27ba4-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27ba4-129">Nachfolgende Aufrufe von Methoden hosting HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="27ba4-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27ba4-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="27ba4-130">Remarks</span></span>  
 <span data-ttu-id="27ba4-131">Die Identität bei Index 0 ist die Identität, die spezifisch für die Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="27ba4-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="27ba4-132">Die Identität bei Index 1 ist die Assembly Neutrale Systemarchitektur für Microsoft intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="27ba4-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="27ba4-133">Die Identität am Index 2 enthält keine Architekturinformationen zu.</span><span class="sxs-lookup"><span data-stu-id="27ba4-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="27ba4-134">`Get` wird in der Regel zweimal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="27ba4-134">`Get` is typically called twice.</span></span> <span data-ttu-id="27ba4-135">Der erste Aufruf stellt einen null-Wert für `pwzBuffer`, und legt `pcchBufferSize` auf die Größe, die für die entsprechenden `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="27ba4-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="27ba4-136">Beim zweiten Aufruf wird ein geeigneter Größe `pwzBuffer`, und enthält Identitätsdaten kanonische Assembly Fertigstellung.</span><span class="sxs-lookup"><span data-stu-id="27ba4-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27ba4-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27ba4-137">Requirements</span></span>  
 <span data-ttu-id="27ba4-138">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27ba4-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27ba4-139">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27ba4-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27ba4-140">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="27ba4-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27ba4-141">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27ba4-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ba4-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27ba4-142">See also</span></span>

- [<span data-ttu-id="27ba4-143">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27ba4-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="27ba4-144">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27ba4-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
