---
title: '&lt;ApplicationPool&gt; -Element (Webeinstellungen)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1a129abca5888120d03c42689ac825d768733a9d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43489941"
---
# <a name="ltapplicationpoolgt-element-web-settings"></a><span data-ttu-id="2551c-102">&lt;ApplicationPool&gt; -Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2551c-102">&lt;applicationPool&gt; Element (Web Settings)</span></span>
<span data-ttu-id="2551c-103">Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, um prozessübergreifende Verhalten zu verwalten, wenn eine ASP.NET-Anwendung im integrierten Modus ausgeführt wird, auf [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="2551c-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2551c-104">Dieses Element und das Feature unterstützt es funktionieren nur, wenn auf Ihrer ASP.NET-Anwendung gehostet wird [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="2551c-104">This element and the feature it supports only work if your ASP.NET application is hosted on [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="2551c-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2551c-105">\<configuration></span></span>  
<span data-ttu-id="2551c-106">\<System.Web >-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2551c-106">\<system.web> Element (Web Settings)</span></span>  
<span data-ttu-id="2551c-107">\<ApplicationPool >-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2551c-107">\<applicationPool> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2551c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2551c-108">Syntax</span></span>  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2551c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2551c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2551c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2551c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2551c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2551c-111">Attributes</span></span>  
  
|<span data-ttu-id="2551c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2551c-112">Attribute</span></span>|<span data-ttu-id="2551c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2551c-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="2551c-114">Gibt an, wie viele gleichzeitige Anforderungen pro CPU ASP.NET erlaubt.</span><span class="sxs-lookup"><span data-stu-id="2551c-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="2551c-115">Gibt an, wie viele gleichzeitige Threads für jede CPU für einen Anwendungspool ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="2551c-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="2551c-116">Dies bietet eine alternative Möglichkeit zum Steuern von ASP.NET Parallelität, da Sie die Anzahl der verwalteten Threads beschränken können, die pro CPU verwendet werden können, um Anforderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2551c-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="2551c-117">Standardmäßig ist diese Einstellung 0, d. h., dass ASP.NET die Anzahl der Threads pro CPU, erstellt werden können, die nicht begrenzt, obwohl die CLR-Threadpool auch die Anzahl der Threads beschränkt, die erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2551c-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="2551c-118">Gibt die maximale Anzahl von Anforderungen, die für ASP.NET in einem einzigen Prozess in die Warteschlange eingereiht werden können.</span><span class="sxs-lookup"><span data-stu-id="2551c-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="2551c-119">Wenn zwei oder mehr ASP.NET-Anwendungen in einen einzelnen Anwendungspool ausführen möchten, unterliegt die kumulative Satz von Anforderungen an jede Anwendung im Anwendungspool, der mit dieser Einstellung.</span><span class="sxs-lookup"><span data-stu-id="2551c-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2551c-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2551c-120">Child Elements</span></span>  
 <span data-ttu-id="2551c-121">Keine</span><span class="sxs-lookup"><span data-stu-id="2551c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2551c-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2551c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2551c-123">Element</span><span class="sxs-lookup"><span data-stu-id="2551c-123">Element</span></span>|<span data-ttu-id="2551c-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2551c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2551c-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="2551c-125">\<system.web></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|<span data-ttu-id="2551c-126">Enthält Informationen zur Interaktion von ASP.NET mit einer hostanwendung.</span><span class="sxs-lookup"><span data-stu-id="2551c-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2551c-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2551c-127">Remarks</span></span>  
 <span data-ttu-id="2551c-128">Beim Ausführen von [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder eine höhere Version im integrierten Modus, diese Kombination Element können Sie konfigurieren, wie ASP.NET Anfragen von Threads und Warteschlangen verwaltet, wenn die Anwendung in einem IIS-Anwendungspool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2551c-128">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="2551c-129">Wenn Sie IIS 6 oder ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] im klassischen Modus oder im ISAPI-Modus, werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="2551c-129">If you run IIS 6 or you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
 <span data-ttu-id="2551c-130">Die `applicationPool` Einstellungen gelten für alle Anwendungspools, die auf eine bestimmte Version von .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2551c-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="2551c-131">Die Einstellungen sind in einer Datei "aspnet.config" enthalten.</span><span class="sxs-lookup"><span data-stu-id="2551c-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="2551c-132">Es gibt eine Version dieser Datei für die Versionen 2.0 und 4.0 von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2551c-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="2551c-133">(Die Versionen 3.0 und 3.5 von .NET Framework Freigeben der Datei "aspnet.config" mit Version 2.0.)</span><span class="sxs-lookup"><span data-stu-id="2551c-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2551c-134">Wenn das Ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] auf [!INCLUDE[win7](../../../../../includes/win7-md.md)], Sie können eine separate aspnet.config-Datei für jeden Anwendungspool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2551c-134">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] on [!INCLUDE[win7](../../../../../includes/win7-md.md)], you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="2551c-135">Dadurch können Sie die Leistung des Threads für jeden Anwendungspool anpassen.</span><span class="sxs-lookup"><span data-stu-id="2551c-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
 <span data-ttu-id="2551c-136">Für die `maxConcurrentRequestsPerCPU` festlegen, die Standardeinstellung "5000" in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effektiv deaktiviert, eine Drosselung der Anforderungen von ASP.NET gesteuert, es sei denn, Sie tatsächlich 5000 oder mehrere Anforderungen pro CPU.</span><span class="sxs-lookup"><span data-stu-id="2551c-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="2551c-137">Die Standardeinstellung hängt stattdessen die CLR-Threadpool Parallelität pro CPU automatisch verwaltet.</span><span class="sxs-lookup"><span data-stu-id="2551c-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="2551c-138">Anwendungen, die machen umfassenden Gebrauch von der Verarbeitung von asynchronen Anforderungen oder viele lang andauernder Anforderungen, die Netzwerk-e/a blockiert deren, profitieren von der erhöhten Standardgrenzwert in die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2551c-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="2551c-139">Festlegen von `maxConcurrentRequestsPerCPU` auf 0 (null) deaktiviert die Verwendung von verwalteten Threads für die Verarbeitung von ASP.NET-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2551c-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="2551c-140">Wenn eine Anwendung in einem IIS-Anwendungspool ausgeführt wird, Anforderungen, die auf dem IIS-e/a-Thread bleiben und aus diesem Grund wird die Parallelität durch die Einstellungen der IIS-Thread gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="2551c-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
 <span data-ttu-id="2551c-141">Die `requestQueueLimit` Einstellung funktioniert genauso wie die `requestQueueLimit` Attribut der [ProcessModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) -Element, das in den Dateien "Web.config" für ASP.NET-Anwendungen festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2551c-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="2551c-142">Allerdings die `requestQueueLimit` Einstellung in einer Datei "aspnet.config" überschreibt die `requestQueueLimit` in einer Datei "Web.config" festlegen.</span><span class="sxs-lookup"><span data-stu-id="2551c-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="2551c-143">Das heißt, wenn beide Attribute festgelegt werden (Dies wird standardmäßig "true"), die `requestQueueLimit` Einstellung in der Datei "aspnet.config" hat Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="2551c-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2551c-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2551c-144">Example</span></span>  
 <span data-ttu-id="2551c-145">Das folgende Beispiel zeigt, wie Sie ASP.NET prozessübergreifende Verhalten in der Datei "aspnet.config" in den folgenden Situationen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2551c-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
-   <span data-ttu-id="2551c-146">Die Anwendung gehostet wird, eine [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] -Anwendungspool.</span><span class="sxs-lookup"><span data-stu-id="2551c-146">The application is hosted in an [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] application pool.</span></span>  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]<span data-ttu-id="2551c-147"> im integrierten Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2551c-147"> is running in Integrated mode.</span></span>  
  
-   <span data-ttu-id="2551c-148">Die Anwendung verwendet die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="2551c-148">The application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span>  
  
 <span data-ttu-id="2551c-149">Die Werte im Beispiel werden die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="2551c-149">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="2551c-150">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="2551c-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2551c-151">Namespace</span><span class="sxs-lookup"><span data-stu-id="2551c-151">Namespace</span></span>||  
|<span data-ttu-id="2551c-152">Schemaname</span><span class="sxs-lookup"><span data-stu-id="2551c-152">Schema Name</span></span>||  
|<span data-ttu-id="2551c-153">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="2551c-153">Validation File</span></span>||  
|<span data-ttu-id="2551c-154">Leer kann sein</span><span class="sxs-lookup"><span data-stu-id="2551c-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="2551c-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2551c-155">See Also</span></span>  
 [<span data-ttu-id="2551c-156">\<system.web>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2551c-156">\<system.web> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
