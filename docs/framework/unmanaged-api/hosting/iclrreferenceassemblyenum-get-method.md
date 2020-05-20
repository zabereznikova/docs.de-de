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
ms.openlocfilehash: 5afa7b37b804b6a11a894e0e6c7708c7787a20ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703363"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="f5663-102">ICLRReferenceAssemblyEnum::Get-Methode</span><span class="sxs-lookup"><span data-stu-id="f5663-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="f5663-103">Ruft die Assemblyidentität am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="f5663-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5663-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5663-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5663-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5663-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="f5663-106">in Der null basierte Index der zurück zugebende Assemblyidentität.</span><span class="sxs-lookup"><span data-stu-id="f5663-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="f5663-107">vorgenommen Ein Puffer mit den Assemblyidentitätsdaten.</span><span class="sxs-lookup"><span data-stu-id="f5663-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="f5663-108">[in, out] Die Größe des `pwzBuffer` Puffers.</span><span class="sxs-lookup"><span data-stu-id="f5663-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5663-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f5663-109">Return Value</span></span>  
  
|<span data-ttu-id="f5663-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5663-110">HRESULT</span></span>|<span data-ttu-id="f5663-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f5663-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5663-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5663-112">S_OK</span></span>|<span data-ttu-id="f5663-113">`Get`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f5663-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="f5663-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f5663-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f5663-115">`pwzBuffer` ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="f5663-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="f5663-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="f5663-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="f5663-117">Die-Enumeration enthält keine weiteren Elemente.</span><span class="sxs-lookup"><span data-stu-id="f5663-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="f5663-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5663-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5663-119">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f5663-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5663-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5663-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5663-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f5663-121">The call timed out.</span></span>|  
|<span data-ttu-id="f5663-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5663-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5663-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f5663-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5663-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5663-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5663-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f5663-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5663-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5663-126">E_FAIL</span></span>|<span data-ttu-id="f5663-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f5663-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5663-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="f5663-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5663-129">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f5663-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5663-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5663-130">Remarks</span></span>  
 <span data-ttu-id="f5663-131">`Get`wird in der Regel zweimal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f5663-131">`Get` is typically called twice.</span></span> <span data-ttu-id="f5663-132">Der erste-Befehl stellt einen NULL-Wert für bereit `pwzBuffer` und legt `pcchBufferSize` auf die für geeignete Größe fest `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="f5663-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="f5663-133">Der zweite-Rückruf stellt eine angemessene Größenanpassung dar `pwzBuffer` und enthält die kanonischen Assemblyidentitätsdaten bei Abschluss.</span><span class="sxs-lookup"><span data-stu-id="f5663-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5663-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5663-134">Requirements</span></span>  
 <span data-ttu-id="f5663-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5663-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5663-136">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f5663-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5663-137">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f5663-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5663-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5663-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5663-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5663-139">See also</span></span>

- [<span data-ttu-id="f5663-140">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5663-140">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f5663-141">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5663-141">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
