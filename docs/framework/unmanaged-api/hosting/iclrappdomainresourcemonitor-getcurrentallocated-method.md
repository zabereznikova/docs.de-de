---
title: ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentAllocated
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentAllocated
helpviewer_keywords:
- GetCurrentAllocated method [.NET Framework hosting]
- ICLRAppDomainResourceMonitor::GetCurrentAllocated method [.NET Framework hosting]
ms.assetid: 7bab209c-efd4-44c2-af30-61abab0ae2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4011881e98c109458bf87efcc1b09463c064f23f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431954"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="40d62-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="40d62-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="40d62-103">Ruft die Gesamtgröße in Bytes aller speicherbelegungen, die von der Anwendungsdomäne seit der Erstellung, ohne Subtraktion des freigegebenen Speichers, die Sammlung veralteter Objekte aufgenommen wurde, vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="40d62-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40d62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40d62-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40d62-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40d62-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="40d62-106">[in] Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="40d62-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="40d62-107">[out] Ein Zeiger auf die Gesamtgröße aller speicherbelegungen.</span><span class="sxs-lookup"><span data-stu-id="40d62-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40d62-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40d62-108">Return Value</span></span>  
 <span data-ttu-id="40d62-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="40d62-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="40d62-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40d62-110">HRESULT</span></span>|<span data-ttu-id="40d62-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40d62-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40d62-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="40d62-112">S_OK</span></span>|<span data-ttu-id="40d62-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="40d62-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="40d62-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="40d62-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="40d62-115">Die Anwendungsdomäne entladen wurde oder nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="40d62-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40d62-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40d62-116">Remarks</span></span>  
 <span data-ttu-id="40d62-117">Diese Methode ist die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="40d62-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40d62-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40d62-118">Requirements</span></span>  
 <span data-ttu-id="40d62-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40d62-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40d62-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="40d62-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="40d62-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="40d62-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40d62-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40d62-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d62-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40d62-123">See Also</span></span>  
 [<span data-ttu-id="40d62-124">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40d62-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [<span data-ttu-id="40d62-125">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="40d62-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)  
 [<span data-ttu-id="40d62-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="40d62-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="40d62-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="40d62-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
