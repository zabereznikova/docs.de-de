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
ms.openlocfilehash: 2ff1f9428a92d091a51a4cca12d69d98da0ecba2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120539"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="87c0d-102">ICLRProbingAssemblyEnum::Get-Methode</span><span class="sxs-lookup"><span data-stu-id="87c0d-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="87c0d-103">Ruft die Assemblyidentität am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="87c0d-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87c0d-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87c0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="87c0d-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="87c0d-106">in Der null basierte Index der zurück zugebende Assemblyidentität.</span><span class="sxs-lookup"><span data-stu-id="87c0d-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="87c0d-107">vorgenommen Ein Puffer mit den Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="87c0d-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="87c0d-108">[in, out] Die Größe des `pwzBuffer` Puffers.</span><span class="sxs-lookup"><span data-stu-id="87c0d-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87c0d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="87c0d-109">Return Value</span></span>  
  
|<span data-ttu-id="87c0d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87c0d-110">HRESULT</span></span>|<span data-ttu-id="87c0d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87c0d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87c0d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="87c0d-112">S_OK</span></span>|<span data-ttu-id="87c0d-113">`Get` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="87c0d-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="87c0d-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="87c0d-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="87c0d-115">`pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="87c0d-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="87c0d-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="87c0d-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="87c0d-117">Die-Enumeration enthält keine weiteren Elemente.</span><span class="sxs-lookup"><span data-stu-id="87c0d-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="87c0d-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87c0d-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87c0d-119">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="87c0d-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87c0d-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87c0d-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87c0d-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="87c0d-121">The call timed out.</span></span>|  
|<span data-ttu-id="87c0d-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87c0d-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87c0d-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="87c0d-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87c0d-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87c0d-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87c0d-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="87c0d-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87c0d-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87c0d-126">E_FAIL</span></span>|<span data-ttu-id="87c0d-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="87c0d-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87c0d-128">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87c0d-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87c0d-129">Nachfolgende Aufrufe an beliebige Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="87c0d-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87c0d-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87c0d-130">Remarks</span></span>  
 <span data-ttu-id="87c0d-131">Die Identität bei Index 0 ist die Identität, die für die Prozessorarchitektur spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="87c0d-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="87c0d-132">Die Identität bei Index 1 ist die Architektur neutrale Assembly für Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="87c0d-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="87c0d-133">Die Identität am Index 2 enthält keine Architektur Informationen.</span><span class="sxs-lookup"><span data-stu-id="87c0d-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="87c0d-134">`Get` wird in der Regel zweimal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="87c0d-134">`Get` is typically called twice.</span></span> <span data-ttu-id="87c0d-135">Der erste-Befehl liefert einen NULL-Wert für `pwzBuffer`und legt `pcchBufferSize` auf die für `pwzBuffer`geeignete Größe fest.</span><span class="sxs-lookup"><span data-stu-id="87c0d-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="87c0d-136">Der zweite-Befehl stellt einen entsprechend großen `pwzBuffer`bereit und enthält die kanonischen Assemblyidentitätsdaten bei Abschluss.</span><span class="sxs-lookup"><span data-stu-id="87c0d-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87c0d-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87c0d-137">Requirements</span></span>  
 <span data-ttu-id="87c0d-138">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87c0d-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87c0d-139">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="87c0d-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87c0d-140">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="87c0d-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87c0d-141">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87c0d-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c0d-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87c0d-142">See also</span></span>

- [<span data-ttu-id="87c0d-143">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87c0d-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="87c0d-144">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87c0d-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
