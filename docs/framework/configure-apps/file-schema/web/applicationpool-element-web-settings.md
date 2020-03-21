---
title: <applicationPool>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152853"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="f0841-102">\<applicationPool>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f0841-102">\<applicationPool> Element (Web Settings)</span></span>
<span data-ttu-id="f0841-103">Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, um prozessweites Verhalten zu verwalten, wenn eine ASP.NET Anwendung im integrierten Modus unter IIS 7.0 oder einer späteren Version ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0841-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f0841-104">Dieses Element und die unterstützte Funktion funktionieren nur, wenn Ihre ASP.NET Anwendung in IIS 7.0 oder neueren Versionen gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f0841-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[<span data-ttu-id="f0841-105">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="f0841-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f0841-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f0841-106">&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)</span></span>  
<span data-ttu-id="f0841-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span><span class="sxs-lookup"><span data-stu-id="f0841-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0841-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0841-108">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0841-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0841-109">Attributes and Elements</span></span>  

<span data-ttu-id="f0841-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0841-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0841-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="f0841-111">Attributes</span></span>  
  
|<span data-ttu-id="f0841-112">attribute</span><span class="sxs-lookup"><span data-stu-id="f0841-112">Attribute</span></span>|<span data-ttu-id="f0841-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0841-113">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="f0841-114">Gibt an, wie viele gleichzeitige Anforderungen ASP.NET pro CPU zulässt.</span><span class="sxs-lookup"><span data-stu-id="f0841-114">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="f0841-115">Gibt an, wie viele gleichzeitige Threads für einen Anwendungspool für jede CPU ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="f0841-115">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="f0841-116">Dies bietet eine alternative Möglichkeit, ASP.NET Parallelität zu steuern, da Sie die Anzahl der verwalteten Threads begrenzen können, die pro CPU verwendet werden können, um Anforderungen zu bedienen.</span><span class="sxs-lookup"><span data-stu-id="f0841-116">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="f0841-117">Standardmäßig ist diese Einstellung 0, was bedeutet, dass ASP.NET die Anzahl der Threads, die pro CPU erstellt werden können, nicht beschränkt, obwohl der CLR-Threadpool auch die Anzahl der Threads begrenzt, die erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="f0841-117">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="f0841-118">Gibt die maximale Anzahl von Anforderungen an, die für ASP.NET in einem einzelnen Prozess in die Warteschlange gestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="f0841-118">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="f0841-119">Wenn zwei oder mehr ASP.NET Anwendungen in einem einzelnen Anwendungspool ausgeführt werden, unterliegt der kumulative Satz von Anforderungen, die an eine Anwendung im Anwendungspool gestellt werden, dieser Einstellung.</span><span class="sxs-lookup"><span data-stu-id="f0841-119">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0841-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0841-120">Child Elements</span></span>  
 <span data-ttu-id="f0841-121">Keine.</span><span class="sxs-lookup"><span data-stu-id="f0841-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0841-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0841-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f0841-123">Element</span><span class="sxs-lookup"><span data-stu-id="f0841-123">Element</span></span>|<span data-ttu-id="f0841-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0841-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0841-125">\<system.web></span><span class="sxs-lookup"><span data-stu-id="f0841-125">\<system.web></span></span>](system-web-element-web-settings.md)|<span data-ttu-id="f0841-126">Enthält Informationen darüber, wie ASP.NET mit einer Hostanwendung interagiert.</span><span class="sxs-lookup"><span data-stu-id="f0841-126">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0841-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f0841-127">Remarks</span></span>  

<span data-ttu-id="f0841-128">Wenn Sie IIS 7.0 oder eine neuere Version im integrierten Modus ausführen, können Sie mit dieser Elementkombination konfigurieren, wie ASP.NET Threads und Warteschlangenanforderungen verwaltet, wenn die Anwendung in einem IIS-Anwendungspool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f0841-128">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="f0841-129">Wenn Sie IIS 6 oder IIS 7.0 im klassischen Modus oder im ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f0841-129">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="f0841-130">Die `applicationPool` Einstellungen gelten für alle Anwendungspools, die auf einer bestimmten Version von .NET Framework ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f0841-130">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="f0841-131">Die Einstellungen sind in einer Datei aspnet.config enthalten.</span><span class="sxs-lookup"><span data-stu-id="f0841-131">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="f0841-132">Es gibt eine Version dieser Datei für die Versionen 2.0 und 4.0 von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f0841-132">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="f0841-133">(Die Versionen 3.0 und 3.5 von .NET Framework teilen sich die Datei aspnet.config mit Version 2.0.)</span><span class="sxs-lookup"><span data-stu-id="f0841-133">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f0841-134">Wenn Sie IIS 7.0 unter Windows 7 ausführen, können Sie für jeden Anwendungspool eine separate aspnet.config-Datei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f0841-134">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="f0841-135">Auf diese Weise können Sie die Leistung der Threads für jeden Anwendungspool anpassen.</span><span class="sxs-lookup"><span data-stu-id="f0841-135">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="f0841-136">Für `maxConcurrentRequestsPerCPU` die Einstellung deaktiviert die Standardeinstellung "5000" in .NET Framework 4 effektiv die Anforderungseinschränkung, die von ASP.NET gesteuert wird, es sei denn, Sie haben tatsächlich 5000 oder mehr Anforderungen pro CPU.</span><span class="sxs-lookup"><span data-stu-id="f0841-136">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="f0841-137">Die Standardeinstellung hängt stattdessen vom CLR-Threadpool ab, um die Parallelität pro CPU automatisch zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f0841-137">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="f0841-138">Anwendungen, die die Verarbeitung asynchroner Anforderungen ausgiebig nutzen oder bei denen viele Langandauernanforderungen für Netzwerk-E/A blockiert sind, profitieren von dem erhöhten Standardlimit in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f0841-138">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="f0841-139">Wenn `maxConcurrentRequestsPerCPU` Sie auf Null setzen, wird die Verwendung von verwalteten Threads für die Verarbeitung ASP.NET Anforderungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0841-139">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="f0841-140">Wenn eine Anwendung in einem IIS-Anwendungspool ausgeführt wird, bleiben Anforderungen im IIS-E/A-Thread, und daher wird die Parallelität durch IIS-Threadeinstellungen gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="f0841-140">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="f0841-141">Die `requestQueueLimit` Einstellung funktioniert auf `requestQueueLimit` die gleiche Weise wie das Attribut des [processModel-Elements,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) das in den Web.config-Dateien für ASP.NET Anwendungen festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f0841-141">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="f0841-142">Die `requestQueueLimit` Einstellung in einer Datei aspnet.config `requestQueueLimit` überschreibt die Einstellung jedoch in einer Web.config-Datei.</span><span class="sxs-lookup"><span data-stu-id="f0841-142">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="f0841-143">Mit anderen Worten, wenn beide Attribute festgelegt sind (standardmäßig `requestQueueLimit` ist dies true), hat die Einstellung in der Datei aspnet.config Vorrang.</span><span class="sxs-lookup"><span data-stu-id="f0841-143">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0841-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0841-144">Example</span></span>  

<span data-ttu-id="f0841-145">Das folgende Beispiel zeigt, wie ASP.NET prozessweiten Verhalten in der Datei aspnet.config unter den folgenden Umständen konfiguriert wird:</span><span class="sxs-lookup"><span data-stu-id="f0841-145">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="f0841-146">Die Anwendung wird in einem IIS 7.0-Anwendungspool gehostet.</span><span class="sxs-lookup"><span data-stu-id="f0841-146">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="f0841-147">IIS 7.0 wird im integrierten Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0841-147">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="f0841-148">Die Anwendung verwendet .NET Framework 3.5 SP1 oder eine neuere Version.</span><span class="sxs-lookup"><span data-stu-id="f0841-148">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="f0841-149">Die Werte im Beispiel sind die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="f0841-149">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="f0841-150">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="f0841-150">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0841-151">Namespace</span><span class="sxs-lookup"><span data-stu-id="f0841-151">Namespace</span></span>||  
|<span data-ttu-id="f0841-152">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="f0841-152">Schema Name</span></span>||  
|<span data-ttu-id="f0841-153">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="f0841-153">Validation File</span></span>||  
|<span data-ttu-id="f0841-154">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="f0841-154">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="f0841-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0841-155">See also</span></span>

- [<span data-ttu-id="f0841-156">\<system.web> Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f0841-156">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
