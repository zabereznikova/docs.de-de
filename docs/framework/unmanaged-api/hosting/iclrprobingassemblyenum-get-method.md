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
ms.openlocfilehash: 9a6145ff2874890f052f18a7e537e20ff259933c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728939"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="fe6e5-102">ICLRProbingAssemblyEnum::Get-Methode</span><span class="sxs-lookup"><span data-stu-id="fe6e5-102">ICLRProbingAssemblyEnum::Get Method</span></span>

<span data-ttu-id="fe6e5-103">Ruft die Assemblyidentität am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe6e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe6e5-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe6e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe6e5-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="fe6e5-106">in Der null basierte Index der zurück zugebende Assemblyidentität.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="fe6e5-107">vorgenommen Ein Puffer mit den Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="fe6e5-108">[in, out] Die Größe des `pwzBuffer` Puffers.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe6e5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fe6e5-109">Return Value</span></span>  
  
|<span data-ttu-id="fe6e5-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe6e5-110">HRESULT</span></span>|<span data-ttu-id="fe6e5-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe6e5-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe6e5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe6e5-112">S_OK</span></span>|<span data-ttu-id="fe6e5-113">`Get` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="fe6e5-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="fe6e5-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="fe6e5-115">`pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="fe6e5-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="fe6e5-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="fe6e5-117">Die-Enumeration enthält keine weiteren Elemente.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="fe6e5-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe6e5-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe6e5-119">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe6e5-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe6e5-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe6e5-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-121">The call timed out.</span></span>|  
|<span data-ttu-id="fe6e5-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe6e5-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe6e5-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe6e5-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe6e5-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe6e5-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe6e5-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe6e5-126">E_FAIL</span></span>|<span data-ttu-id="fe6e5-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe6e5-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe6e5-129">Nachfolgende Aufrufe an beliebige Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe6e5-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe6e5-130">Remarks</span></span>  

 <span data-ttu-id="fe6e5-131">Die Identität bei Index 0 ist die Identität, die für die Prozessorarchitektur spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="fe6e5-132">Die Identität bei Index 1 ist die Architektur neutrale Assembly für Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="fe6e5-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="fe6e5-133">Die Identität am Index 2 enthält keine Architektur Informationen.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="fe6e5-134">`Get` wird in der Regel zweimal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-134">`Get` is typically called twice.</span></span> <span data-ttu-id="fe6e5-135">Der erste-Befehl stellt einen NULL-Wert für bereit `pwzBuffer` und legt `pcchBufferSize` auf die für geeignete Größe fest `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="fe6e5-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="fe6e5-136">Der zweite-Rückruf stellt eine angemessene Größenanpassung dar `pwzBuffer` und enthält die kanonischen Assemblyidentitätsdaten bei Abschluss.</span><span class="sxs-lookup"><span data-stu-id="fe6e5-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe6e5-137">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fe6e5-137">Requirements</span></span>  

 <span data-ttu-id="fe6e5-138">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe6e5-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe6e5-139">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fe6e5-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe6e5-140">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fe6e5-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe6e5-141">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe6e5-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6e5-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe6e5-142">See also</span></span>

- [<span data-ttu-id="fe6e5-143">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe6e5-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="fe6e5-144">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe6e5-144">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
