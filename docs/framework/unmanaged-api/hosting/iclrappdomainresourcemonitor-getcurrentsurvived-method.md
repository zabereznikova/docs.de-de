---
title: ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentSurvived
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentSurvived method [.NET Framework hosting]
- GetCurrentSurvived method [.NET Framework hosting]
ms.assetid: 392e9009-40ef-40e3-ad4d-7ce93a989e78
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a24f51884b5dc55e45d22f33735fe07db770d06
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466912"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="67258-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode</span><span class="sxs-lookup"><span data-stu-id="67258-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="67258-103">Ruft die Anzahl der Bytes, die die letzte vollständigen blockierenden Garbagecollection noch vorhanden sind und verwiesen wird, werden von der aktuellen Anwendungsdomäne, ab.</span><span class="sxs-lookup"><span data-stu-id="67258-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67258-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67258-104">Syntax</span></span>  
  
```  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67258-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67258-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="67258-106">[in] Die ID des angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="67258-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="67258-107">[out] Ein Zeiger auf die Anzahl der Bytes, die nach der letzten Garbagecollection noch vorhanden, die von dieser Anwendungsdomäne gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="67258-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="67258-108">Ist nach einer vollständigen Auflistung stellt diese Anzahl richtig und vollständig.</span><span class="sxs-lookup"><span data-stu-id="67258-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="67258-109">Nach einer kurzlebiger Auflistung ist ist diese Zahl möglicherweise unvollständig.</span><span class="sxs-lookup"><span data-stu-id="67258-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="67258-110">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="67258-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="67258-111">[out] Ein Zeiger auf die Gesamtzahl der Bytes, die von der letzten Garbagecollection noch vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="67258-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="67258-112">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes, die in verwalteten Heaps gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="67258-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="67258-113">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes, die in kurzlebigen Generationen live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="67258-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="67258-114">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="67258-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67258-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="67258-115">Return Value</span></span>  
 <span data-ttu-id="67258-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="67258-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="67258-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67258-117">HRESULT</span></span>|<span data-ttu-id="67258-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67258-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67258-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="67258-119">S_OK</span></span>|<span data-ttu-id="67258-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="67258-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="67258-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="67258-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="67258-122">Die Anwendungsdomäne entladen wurde, oder es ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="67258-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67258-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67258-123">Remarks</span></span>  
 <span data-ttu-id="67258-124">Statistiken werden nur nach einer vollständigen blockierenden Garbagecollection aktualisiert. Tritt auf, d. h. eine Auflistung, die alle Generationen umfasst, und Beenden der Anwendung während der Auflistung, an.</span><span class="sxs-lookup"><span data-stu-id="67258-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="67258-125">Z. B. die <xref:System.GC.Collect?displayProperty=nameWithType> -methodenüberladung, führt eine vollständige blockierende Auflistung.</span><span class="sxs-lookup"><span data-stu-id="67258-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="67258-126">Gleichzeitige Garbagecollection erfolgt im Hintergrund und die Anwendung nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="67258-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="67258-127">Die `GetCurrentSurvived` Methode ist, die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="67258-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67258-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67258-128">Requirements</span></span>  
 <span data-ttu-id="67258-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67258-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67258-130">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="67258-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="67258-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="67258-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67258-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67258-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67258-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67258-133">See also</span></span>
- [<span data-ttu-id="67258-134">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67258-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="67258-135">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="67258-135">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="67258-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="67258-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="67258-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="67258-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
