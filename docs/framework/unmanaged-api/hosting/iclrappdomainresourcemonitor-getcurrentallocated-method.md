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
ms.openlocfilehash: 7fcd7a3aa1a6c034985099c24071429384563700
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129388"
---
# <a name="iclrappdomainresourcemonitorgetcurrentallocated-method"></a><span data-ttu-id="7d326-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="7d326-102">ICLRAppDomainResourceMonitor::GetCurrentAllocated Method</span></span>
<span data-ttu-id="7d326-103">Ruft die Gesamtgröße in Bytes aller speicherbelegungen, die von der Anwendungsdomäne seit der Erstellung, ohne Subtraktion des freigegebenen Speichers, der Garbage Collection durchgeführt wurde, vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="7d326-103">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d326-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d326-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAllocated([in]  DWORD dwAppDomainId,  
                            [out] ULONGLONG* pBytesAllocated);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d326-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d326-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="7d326-106">[in] Die ID des angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="7d326-106">[in] The ID of the requested application domain.</span></span>  
  
 `pBytesAllocated`  
 <span data-ttu-id="7d326-107">[out] Ein Zeiger auf die Gesamtgröße aller speicherbelegungen.</span><span class="sxs-lookup"><span data-stu-id="7d326-107">[out] A pointer to the total size of all memory allocations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d326-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d326-108">Return Value</span></span>  
 <span data-ttu-id="7d326-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d326-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7d326-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7d326-110">HRESULT</span></span>|<span data-ttu-id="7d326-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d326-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d326-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7d326-112">S_OK</span></span>|<span data-ttu-id="7d326-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7d326-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="7d326-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="7d326-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="7d326-115">Die Anwendungsdomäne entladen wurde, oder es ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7d326-115">The application domain has been unloaded or does not exist.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d326-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d326-116">Remarks</span></span>  
 <span data-ttu-id="7d326-117">Diese Methode ist, die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7d326-117">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d326-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d326-118">Requirements</span></span>  
 <span data-ttu-id="7d326-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d326-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d326-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7d326-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7d326-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7d326-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d326-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d326-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d326-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d326-123">See also</span></span>

- [<span data-ttu-id="7d326-124">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d326-124">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="7d326-125">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="7d326-125">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="7d326-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d326-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7d326-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="7d326-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
