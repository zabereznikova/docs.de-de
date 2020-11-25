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
ms.openlocfilehash: eba9caece91e369cd46aed652b559ace49c77725
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704904"
---
# <a name="iclrappdomainresourcemonitorgetcurrentsurvived-method"></a><span data-ttu-id="6d440-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived-Methode</span><span class="sxs-lookup"><span data-stu-id="6d440-102">ICLRAppDomainResourceMonitor::GetCurrentSurvived Method</span></span>

<span data-ttu-id="6d440-103">Ruft die Anzahl der Bytes ab, die die letzte vollständige Blockierung Garbage Collection und auf die von der aktuellen Anwendungsdomäne verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6d440-103">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d440-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d440-104">Syntax</span></span>  
  
```cpp  
HRESULT STDMETHODCALLTYPE GetCurrentSurvived(  
             [in]  DWORD dwAppDomainId,  
             [out] ULONGLONG *pAppDomainBytesSurvived,  
             [out] ULONGLONG *pTotalBytesSurvived);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d440-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d440-105">Parameters</span></span>  

 `dwAppDomainId`  
 <span data-ttu-id="6d440-106">in Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6d440-106">[in] The ID of the requested application domain.</span></span>  
  
 `pAppDomainBytesSurvived`  
 <span data-ttu-id="6d440-107">vorgenommen Ein Zeiger auf die Anzahl der Bytes, die nach der letzten Garbage Collection, die von dieser Anwendungsdomäne aufbewahrt werden, noch nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d440-107">[out] A pointer to the number of bytes that survived after the last garbage collection that are held by this application domain.</span></span> <span data-ttu-id="6d440-108">Nach einer vollständigen Sammlung ist diese Zahl genau und vollständig.</span><span class="sxs-lookup"><span data-stu-id="6d440-108">After a full collection, this number is accurate and complete.</span></span> <span data-ttu-id="6d440-109">Nach einer kurzlebigen Auflistung ist diese Zahl potenziell unvollständig.</span><span class="sxs-lookup"><span data-stu-id="6d440-109">After an ephemeral collection, this number is potentially incomplete.</span></span> <span data-ttu-id="6d440-110">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="6d440-110">This parameter can be `null`.</span></span>  
  
 `pRuntimeBytesSurvived`  
 <span data-ttu-id="6d440-111">vorgenommen Ein Zeiger auf die Gesamtanzahl der Bytes, die seit dem letzten Garbage Collection noch nicht angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="6d440-111">[out] A pointer to the total number of bytes that survived from the last garbage collection.</span></span> <span data-ttu-id="6d440-112">Nach einer vollständigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in verwalteten Heaps aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="6d440-112">After a full collection, this number represents the number of the bytes that are held in managed heaps.</span></span> <span data-ttu-id="6d440-113">Nach einer kurzlebigen Auflistung stellt diese Anzahl die Anzahl der Bytes dar, die in kurzlebigen Generationen Live gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6d440-113">After an ephemeral collection, this number represents the number of bytes that are held live in ephemeral generations.</span></span> <span data-ttu-id="6d440-114">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="6d440-114">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d440-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6d440-115">Return Value</span></span>  

 <span data-ttu-id="6d440-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d440-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6d440-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d440-117">HRESULT</span></span>|<span data-ttu-id="6d440-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d440-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d440-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d440-119">S_OK</span></span>|<span data-ttu-id="6d440-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6d440-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="6d440-121">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="6d440-121">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="6d440-122">Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6d440-122">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d440-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d440-123">Remarks</span></span>  

 <span data-ttu-id="6d440-124">Statistiken werden erst nach einem vollen, blockierenden Garbage Collection aktualisiert. Das heißt, eine Auflistung, die alle Generationen einschließt und die Anwendung beendet, während die Auflistung auftritt.</span><span class="sxs-lookup"><span data-stu-id="6d440-124">Statistics are updated only after a full, blocking garbage collection; that is, a collection that includes all generations and that stops the application while collection occurs.</span></span> <span data-ttu-id="6d440-125">Die- <xref:System.GC.Collect?displayProperty=nameWithType> Methoden Überladung führt z. b. eine vollständige blockierende Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="6d440-125">For example, the <xref:System.GC.Collect?displayProperty=nameWithType> method overload performs a full, blocking collection.</span></span> <span data-ttu-id="6d440-126">Gleichzeitige Garbage Collection treten im Hintergrund auf und blockieren die Anwendung nicht.</span><span class="sxs-lookup"><span data-stu-id="6d440-126">Concurrent garbage collection occurs in the background and does not block the application.</span></span>  
  
 <span data-ttu-id="6d440-127">Die- `GetCurrentSurvived` Methode ist das nicht verwaltete Äquivalent der verwalteten- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6d440-127">The `GetCurrentSurvived` method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d440-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6d440-128">Requirements</span></span>  

 <span data-ttu-id="6d440-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d440-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d440-130">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="6d440-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6d440-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6d440-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d440-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d440-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d440-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d440-133">See also</span></span>

- [<span data-ttu-id="6d440-134">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d440-134">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="6d440-135">Überwachung von Anwendungs Domänen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6d440-135">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="6d440-136">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6d440-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="6d440-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="6d440-137">Hosting</span></span>](index.md)
