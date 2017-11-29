---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9fe624c83be5dcf762f1c6036f8e4264f0e45c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="23c22-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode</span><span class="sxs-lookup"><span data-stu-id="23c22-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="23c22-103">Ruft die Anzahl der Bytes, die die letzte vollständige blockierende Garbagecollection noch vorhanden sind und verwiesen wird, werden von der aktuellen Anwendungsdomäne, ab.</span><span class="sxs-lookup"><span data-stu-id="23c22-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23c22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23c22-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23c22-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23c22-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="23c22-106">[in] Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="23c22-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="23c22-107">[out] Ein Zeiger auf die Anzahl der Bytes, die nach der letzten Garbagecollection noch vorhanden sind, die von dieser Anwendungsdomäne gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="23c22-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="23c22-108">Nach einer vollständigen Auflistung ist diese Nummer genauer und vollständiger.</span><span class="sxs-lookup"><span data-stu-id="23c22-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="23c22-109">Nach einer kurzlebigen Auflistung ist diese Nummer möglicherweise unvollständig.</span><span class="sxs-lookup"><span data-stu-id="23c22-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="23c22-110">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="23c22-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="23c22-111">[out] Ein Zeiger auf die Gesamtanzahl der Bytes, die von der letzten Garbagecollection noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="23c22-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="23c22-112">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes, die in verwalteten Heaps gehalten werden.</span><span class="sxs-lookup"><span data-stu-id="23c22-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="23c22-113">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="23c22-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="23c22-114">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="23c22-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23c22-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23c22-115">Return Value</span></span>  
 <span data-ttu-id="23c22-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="23c22-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="23c22-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23c22-117">HRESULT</span></span>|<span data-ttu-id="23c22-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23c22-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23c22-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="23c22-119">S_OK</span></span>|<span data-ttu-id="23c22-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="23c22-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="23c22-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="23c22-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="23c22-122">Die Anwendungsdomäne entladen wurde oder nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="23c22-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23c22-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23c22-123">Remarks</span></span>  
 <span data-ttu-id="23c22-124">Statistiken werden erst nach eine vollständige blockierende Garbagecollection aktualisiert. Tritt auf, d. h. eine Auflistung, die alle Generationen umfasst, und Beenden der Anwendung während der Auflistung, an.</span><span class="sxs-lookup"><span data-stu-id="23c22-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="23c22-125">Z. B. die <xref:System.GC.Collect?displayProperty=nameWithType> methodenüberladung führt eine vollständige blockierende Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="23c22-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="23c22-126">Die gleichzeitige Garbagecollection erfolgt im Hintergrund und die Anwendung nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="23c22-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="23c22-127">Die `GetCurrentSurvived` Methode ist die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="23c22-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23c22-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23c22-128">Requirements</span></span>  
 <span data-ttu-id="23c22-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c22-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c22-130">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="23c22-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="23c22-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23c22-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23c22-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23c22-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c22-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23c22-133">See Also</span></span>  
 [<span data-ttu-id="23c22-134">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23c22-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="23c22-135">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="23c22-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="23c22-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="23c22-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="23c22-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="23c22-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
