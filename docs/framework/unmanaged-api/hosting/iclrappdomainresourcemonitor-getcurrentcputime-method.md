---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8022428c7f803f96e2fa150588edf95542bf19b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985217"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="96c63-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode</span><span class="sxs-lookup"><span data-stu-id="96c63-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="96c63-103">Ruft die gesamte Prozessorzeit, die von allen Threads beim Ausführen in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="96c63-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96c63-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96c63-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="96c63-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="96c63-106">[in] Die ID des angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="96c63-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="96c63-107">[out] Ein Zeiger auf die gesamte Prozessorzeit, die von allen Threads beim Ausführen in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="96c63-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="96c63-108">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="96c63-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96c63-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="96c63-109">Return Value</span></span>  
  
|<span data-ttu-id="96c63-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96c63-110">HRESULT</span></span>|<span data-ttu-id="96c63-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96c63-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96c63-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="96c63-112">S_OK</span></span>|<span data-ttu-id="96c63-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="96c63-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="96c63-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="96c63-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="96c63-115">Die Anwendungsdomäne entladen wurde, oder es ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="96c63-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="96c63-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96c63-116">E_FAIL</span></span>|<span data-ttu-id="96c63-117">Ressourcenüberwachung der Anwendungsdomäne ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="96c63-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="96c63-118">- oder - </span><span class="sxs-lookup"><span data-stu-id="96c63-118">-or-</span></span><br /><br /> <span data-ttu-id="96c63-119">Alle anderen Fehler.</span><span class="sxs-lookup"><span data-stu-id="96c63-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96c63-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96c63-120">Remarks</span></span>  
 <span data-ttu-id="96c63-121">Diese Methode ist, die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="96c63-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96c63-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96c63-122">Requirements</span></span>  
 <span data-ttu-id="96c63-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96c63-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96c63-124">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="96c63-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="96c63-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="96c63-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96c63-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96c63-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c63-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96c63-127">See also</span></span>

- [<span data-ttu-id="96c63-128">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96c63-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="96c63-129">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="96c63-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="96c63-130">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="96c63-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="96c63-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="96c63-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
