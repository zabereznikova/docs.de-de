---
title: ICLRRuntimeHost::GetCurrentAppDomainId-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCurrentAppDomainId
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 001a467536c899c3849b5689e65bdaf404beab75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="e5cbd-102">ICLRRuntimeHost::GetCurrentAppDomainId-Methode</span><span class="sxs-lookup"><span data-stu-id="e5cbd-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="e5cbd-103">Ruft den numerischen Bezeichner von die <xref:System.AppDomain> , die gerade ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5cbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5cbd-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5cbd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5cbd-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="e5cbd-106">[out] Den numerischen Bezeichner von die <xref:System.AppDomain> , die gerade ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5cbd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e5cbd-107">Return Value</span></span>  
  
|<span data-ttu-id="e5cbd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5cbd-108">HRESULT</span></span>|<span data-ttu-id="e5cbd-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5cbd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5cbd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5cbd-110">S_OK</span></span>|<span data-ttu-id="e5cbd-111">`GetCurrentAppDomainId`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="e5cbd-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="e5cbd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5cbd-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e5cbd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5cbd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5cbd-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-115">The call timed out.</span></span>|  
|<span data-ttu-id="e5cbd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5cbd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5cbd-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5cbd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5cbd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5cbd-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5cbd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5cbd-120">E_FAIL</span></span>|<span data-ttu-id="e5cbd-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5cbd-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5cbd-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5cbd-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5cbd-124">Remarks</span></span>  
 <span data-ttu-id="e5cbd-125">Die `pdwAppDomainId` Parameter festgelegt ist, auf den Wert des der <xref:System.AppDomain.Id%2A> Eigenschaft von der <xref:System.AppDomain> in die der aktuelle Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e5cbd-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5cbd-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5cbd-126">Requirements</span></span>  
 <span data-ttu-id="e5cbd-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5cbd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5cbd-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5cbd-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5cbd-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e5cbd-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5cbd-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5cbd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5cbd-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5cbd-131">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="e5cbd-132">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5cbd-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
