---
title: ICLRAppDomainResourceMonitor-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
ms.openlocfilehash: 208d567aa5c19ddcf8bf9b13b452cb4fc48c976f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126764"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="18b85-102">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18b85-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="18b85-103">Stellt Methoden bereit, die den Arbeitsspeicher und die CPU-Auslastung einer Anwendungsdomäne überprüfen.</span><span class="sxs-lookup"><span data-stu-id="18b85-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18b85-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="18b85-104">Methods</span></span>  
  
|<span data-ttu-id="18b85-105">Methode</span><span class="sxs-lookup"><span data-stu-id="18b85-105">Method</span></span>|<span data-ttu-id="18b85-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18b85-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18b85-107">GetCurrentAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="18b85-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="18b85-108">Ruft die Gesamtgröße (in Bytes) aller Speicher Belegungen ab, die von der Anwendungsdomäne seit der Erstellung vorgenommen wurden, ohne Subtraktion von Speicher, der in die Garbage Collection aufgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="18b85-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="18b85-109">GetCurrentSurvived-Methode</span><span class="sxs-lookup"><span data-stu-id="18b85-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="18b85-110">Ruft die Anzahl der Bytes ab, die die letzte vollständige Blockierung Garbage Collection und auf die von der aktuellen Anwendungsdomäne verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="18b85-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="18b85-111">GetCurrentCpuTime-Methode</span><span class="sxs-lookup"><span data-stu-id="18b85-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="18b85-112">Ruft die gesamte Prozessorzeit ab, die während der Ausführung in der aktuellen Anwendungsdomäne von allen Threads verwendet wurde, seit die Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="18b85-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18b85-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18b85-113">Remarks</span></span>  
 <span data-ttu-id="18b85-114">Die `ICLRAppDomainResourceMonitor`-Schnittstelle bietet ähnliche Funktionen wie die folgenden verwalteten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="18b85-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="18b85-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18b85-115">Requirements</span></span>  
 <span data-ttu-id="18b85-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18b85-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18b85-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="18b85-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="18b85-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="18b85-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18b85-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18b85-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b85-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18b85-120">See also</span></span>

- [<span data-ttu-id="18b85-121">\<appdomainresourcemonitoring > Element</span><span class="sxs-lookup"><span data-stu-id="18b85-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="18b85-122">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="18b85-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="18b85-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="18b85-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="18b85-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="18b85-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
