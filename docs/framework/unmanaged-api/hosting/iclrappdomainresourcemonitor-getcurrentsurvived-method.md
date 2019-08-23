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
ms.openlocfilehash: bf285b6e1f703c8776937fa33c7ab5801f04f80f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950159"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="8a7d4-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode</span><span class="sxs-lookup"><span data-stu-id="8a7d4-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>
<span data-ttu-id="8a7d4-103">Ruft die Anzahl der Bytes ab, die die letzte vollständige Blockierung Garbage Collection und auf die von der aktuellen Anwendungsdomäne verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a7d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a7d4-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a7d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a7d4-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="8a7d4-106">in Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="8a7d4-107">vorgenommen Ein Zeiger auf die Anzahl der Bytes, die nach der letzten Garbage Collection, die von dieser Anwendungsdomäne aufbewahrt werden, noch nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="8a7d4-108">Nach einer vollständigen Sammlung ist diese Zahl genau und vollständig.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="8a7d4-109">Nach einer kurzlebigen Auflistung ist diese Zahl potenziell unvollständig.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="8a7d4-110">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="8a7d4-111">vorgenommen Ein Zeiger auf die Gesamtanzahl der Bytes, die seit dem letzten Garbage Collection noch nicht angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="8a7d4-112">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="8a7d4-113">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen Live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="8a7d4-114">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a7d4-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8a7d4-115">Return Value</span></span>  
 <span data-ttu-id="8a7d4-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8a7d4-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a7d4-117">HRESULT</span></span>|<span data-ttu-id="8a7d4-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a7d4-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a7d4-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a7d4-119">S_OK</span></span>|<span data-ttu-id="8a7d4-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="8a7d4-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="8a7d4-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="8a7d4-122">Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a7d4-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a7d4-123">Remarks</span></span>  
 <span data-ttu-id="8a7d4-124">Statistiken werden erst nach einem vollen, blockierenden Garbage Collection aktualisiert. Das heißt, eine Auflistung, die alle Generationen einschließt und die Anwendung beendet, während die Auflistung auftritt.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="8a7d4-125">Die <xref:System.GC.Collect?displayProperty=nameWithType> -Methoden Überladung führt z. b. eine vollständige blockierende Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="8a7d4-126">Gleichzeitige Garbage Collection treten im Hintergrund auf und blockieren die Anwendung nicht.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="8a7d4-127">Die `GetCurrentSurvived` -Methode ist das nicht verwaltete Äquivalent der verwalteten <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8a7d4-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a7d4-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a7d4-128">Requirements</span></span>  
 <span data-ttu-id="8a7d4-129">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a7d4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a7d4-130">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8a7d4-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8a7d4-131">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8a7d4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a7d4-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a7d4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7d4-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a7d4-133">See also</span></span>

- [<span data-ttu-id="8a7d4-134">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a7d4-134">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="8a7d4-135">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="8a7d4-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="8a7d4-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8a7d4-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8a7d4-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="8a7d4-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
