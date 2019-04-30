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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15bdbc001838e3d13a9789c8f54daa80f3b6ef9a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985204"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="2ec19-102">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ec19-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="2ec19-103">Bietet Methoden, die einer Anwendungsdomäne Arbeitsspeicher- und CPU-Auslastung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2ec19-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ec19-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2ec19-104">Methods</span></span>  
  
|<span data-ttu-id="2ec19-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2ec19-105">Method</span></span>|<span data-ttu-id="2ec19-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ec19-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ec19-107">GetCurrentAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="2ec19-107">GetCurrentAllocated Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="2ec19-108">Ruft die Gesamtgröße in Bytes aller speicherbelegungen, die von der Anwendungsdomäne seit der Erstellung, ohne Subtraktion des freigegebenen Speichers, der Garbage Collection durchgeführt wurde, vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="2ec19-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="2ec19-109">GetCurrentSurvived-Methode</span><span class="sxs-lookup"><span data-stu-id="2ec19-109">GetCurrentSurvived Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="2ec19-110">Ruft die Anzahl der Bytes, die die letzte vollständigen blockierenden Garbagecollection noch vorhanden sind und verwiesen wird, werden von der aktuellen Anwendungsdomäne, ab.</span><span class="sxs-lookup"><span data-stu-id="2ec19-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="2ec19-111">GetCurrentCpuTime-Methode</span><span class="sxs-lookup"><span data-stu-id="2ec19-111">GetCurrentCpuTime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="2ec19-112">Ruft die gesamte Prozessorzeit, die von allen Threads beim Ausführen in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2ec19-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ec19-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ec19-113">Remarks</span></span>  
 <span data-ttu-id="2ec19-114">Die `ICLRAppDomainResourceMonitor` Schnittstelle bietet Funktionen, die in den folgenden verwalteten Eigenschaften ähnelt:</span><span class="sxs-lookup"><span data-stu-id="2ec19-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="2ec19-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ec19-115">Requirements</span></span>  
 <span data-ttu-id="2ec19-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ec19-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ec19-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="2ec19-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2ec19-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2ec19-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ec19-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ec19-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ec19-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ec19-120">See also</span></span>

- [<span data-ttu-id="2ec19-121">\<AppDomainResourceMonitoring >-Element</span><span class="sxs-lookup"><span data-stu-id="2ec19-121">\<appDomainResourceMonitoring> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="2ec19-122">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="2ec19-122">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="2ec19-123">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2ec19-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2ec19-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="2ec19-124">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
