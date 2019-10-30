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
ms.openlocfilehash: de57fec05c338e51d0691ccfa0d0bffb334848de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126786"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="9e8a3-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode</span><span class="sxs-lookup"><span data-stu-id="9e8a3-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="9e8a3-103">Ruft die gesamte Prozessorzeit ab, die während der Ausführung in der aktuellen Anwendungsdomäne von allen Threads verwendet wurde, seit die Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e8a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e8a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e8a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e8a3-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="9e8a3-106">in Die ID der angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="9e8a3-107">vorgenommen Ein Zeiger auf die gesamte Prozessorzeit, die von allen Threads während der Ausführung in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="9e8a3-108">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e8a3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9e8a3-109">Return Value</span></span>  
  
|<span data-ttu-id="9e8a3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e8a3-110">HRESULT</span></span>|<span data-ttu-id="9e8a3-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e8a3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e8a3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e8a3-112">S_OK</span></span>|<span data-ttu-id="9e8a3-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="9e8a3-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="9e8a3-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="9e8a3-115">Die Anwendungsdomäne wurde entladen oder ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="9e8a3-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e8a3-116">E_FAIL</span></span>|<span data-ttu-id="9e8a3-117">Die Überwachung der Anwendungs Domänen Ressource ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="9e8a3-118">- oder -</span><span class="sxs-lookup"><span data-stu-id="9e8a3-118">-or-</span></span><br /><br /> <span data-ttu-id="9e8a3-119">Alle anderen Fehler.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e8a3-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e8a3-120">Remarks</span></span>  
 <span data-ttu-id="9e8a3-121">Diese Methode ist die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9e8a3-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e8a3-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e8a3-122">Requirements</span></span>  
 <span data-ttu-id="9e8a3-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e8a3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e8a3-124">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="9e8a3-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9e8a3-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9e8a3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e8a3-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e8a3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e8a3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e8a3-127">See also</span></span>

- [<span data-ttu-id="9e8a3-128">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e8a3-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="9e8a3-129">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9e8a3-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9e8a3-130">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="9e8a3-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="9e8a3-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="9e8a3-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
