---
title: ICLRRuntimeHost::GetCurrentAppDomainId-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
ms.openlocfilehash: 1c667b19ac4bfa0bea95b85cf099906e351e5b71
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703672"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="8c9ab-102">ICLRRuntimeHost::GetCurrentAppDomainId-Methode</span><span class="sxs-lookup"><span data-stu-id="8c9ab-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="8c9ab-103">Ruft den numerischen Bezeichner der ab <xref:System.AppDomain> , die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c9ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c9ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c9ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c9ab-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="8c9ab-106">vorgenommen Der numerische Bezeichner der <xref:System.AppDomain> , die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c9ab-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8c9ab-107">Return Value</span></span>  
  
|<span data-ttu-id="8c9ab-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c9ab-108">HRESULT</span></span>|<span data-ttu-id="8c9ab-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c9ab-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c9ab-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c9ab-110">S_OK</span></span>|<span data-ttu-id="8c9ab-111">`GetCurrentAppDomainId`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="8c9ab-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c9ab-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c9ab-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c9ab-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c9ab-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c9ab-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-115">The call timed out.</span></span>|  
|<span data-ttu-id="8c9ab-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c9ab-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c9ab-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c9ab-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c9ab-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c9ab-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c9ab-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c9ab-120">E_FAIL</span></span>|<span data-ttu-id="8c9ab-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c9ab-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c9ab-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c9ab-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c9ab-124">Remarks</span></span>  
 <span data-ttu-id="8c9ab-125">Der- `pdwAppDomainId` Parameter wird auf den Wert der- <xref:System.AppDomain.Id%2A> Eigenschaft der festgelegt, in der <xref:System.AppDomain> der aktuelle Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c9ab-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c9ab-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c9ab-126">Requirements</span></span>  
 <span data-ttu-id="8c9ab-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c9ab-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c9ab-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8c9ab-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c9ab-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8c9ab-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c9ab-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c9ab-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9ab-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c9ab-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="8c9ab-132">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c9ab-132">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
