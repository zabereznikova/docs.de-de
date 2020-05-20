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
ms.openlocfilehash: 08dc0f0891d960cb7b402b30455e606aaff7bcea
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616007"
---
# <a name="iclrappdomainresourcemonitor-interface"></a><span data-ttu-id="d59cb-102">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d59cb-102">ICLRAppDomainResourceMonitor Interface</span></span>
<span data-ttu-id="d59cb-103">Stellt Methoden bereit, die den Arbeitsspeicher und die CPU-Auslastung einer Anwendungsdomäne überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d59cb-103">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d59cb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d59cb-104">Methods</span></span>  
  
|<span data-ttu-id="d59cb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d59cb-105">Method</span></span>|<span data-ttu-id="d59cb-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d59cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d59cb-107">GetCurrentAllocated-Methode</span><span class="sxs-lookup"><span data-stu-id="d59cb-107">GetCurrentAllocated Method</span></span>](iclrappdomainresourcemonitor-getcurrentallocated-method.md)|<span data-ttu-id="d59cb-108">Ruft die Gesamtgröße (in Bytes) aller Speicher Belegungen ab, die von der Anwendungsdomäne seit der Erstellung vorgenommen wurden, ohne Subtraktion von Speicher, der in die Garbage Collection aufgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="d59cb-108">Gets the total size, in bytes, of all memory allocations that have been made by the application domain since it was created, without subtracting memory that has been garbage-collected.</span></span>|  
|[<span data-ttu-id="d59cb-109">GetCurrentSurvived-Methode</span><span class="sxs-lookup"><span data-stu-id="d59cb-109">GetCurrentSurvived Method</span></span>](iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|<span data-ttu-id="d59cb-110">Ruft die Anzahl der Bytes ab, die die letzte vollständige Blockierung Garbage Collection und auf die von der aktuellen Anwendungsdomäne verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d59cb-110">Gets the number of bytes that survived the last full, blocking garbage collection and that are referenced by the current application domain.</span></span>|  
|[<span data-ttu-id="d59cb-111">GetCurrentCpuTime-Methode</span><span class="sxs-lookup"><span data-stu-id="d59cb-111">GetCurrentCpuTime Method</span></span>](iclrappdomainresourcemonitor-getcurrentcputime-method.md)|<span data-ttu-id="d59cb-112">Ruft die gesamte Prozessorzeit ab, die während der Ausführung in der aktuellen Anwendungsdomäne von allen Threads verwendet wurde, seit die Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d59cb-112">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d59cb-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d59cb-113">Remarks</span></span>  
 <span data-ttu-id="d59cb-114">Die- `ICLRAppDomainResourceMonitor` Schnittstelle bietet eine ähnliche Funktionalität wie die folgenden verwalteten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d59cb-114">The `ICLRAppDomainResourceMonitor` interface provides functionality that is similar to the following managed properties:</span></span>  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a><span data-ttu-id="d59cb-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d59cb-115">Requirements</span></span>  
 <span data-ttu-id="d59cb-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d59cb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d59cb-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="d59cb-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d59cb-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d59cb-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d59cb-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d59cb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d59cb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d59cb-120">See also</span></span>

- [<span data-ttu-id="d59cb-121">\<appdomainresourcemonitoring-> Element</span><span class="sxs-lookup"><span data-stu-id="d59cb-121">\<appDomainResourceMonitoring> Element</span></span>](../../configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [<span data-ttu-id="d59cb-122">Überwachung von Anwendungs Domänen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d59cb-122">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="d59cb-123">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d59cb-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d59cb-124">Hosting</span><span class="sxs-lookup"><span data-stu-id="d59cb-124">Hosting</span></span>](index.md)
