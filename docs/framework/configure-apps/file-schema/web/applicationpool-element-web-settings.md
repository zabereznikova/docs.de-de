---
title: <applicationPool>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 963b25e57ae8c2cc59dcc3e50ae2a52cc04f54a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185638"
---
# <a name="applicationpool-element-web-settings"></a><span data-ttu-id="98d7e-102">\<applicationPool>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="98d7e-102">\<applicationPool> Element (Web Settings)</span></span>

<span data-ttu-id="98d7e-103">Gibt Konfigurationseinstellungen an, die von ASP.NET verwendet werden, um Prozess weites Verhalten zu verwalten, wenn eine ASP.NET-Anwendung im integrierten Modus unter IIS 7,0 oder einer höheren Version ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98d7e-103">Specifies configuration settings that are used by ASP.NET to manage process-wide behavior when an ASP.NET application is running in Integrated mode on IIS 7.0 or a later version.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="98d7e-104">Dieses Element und die Funktion, die es unterstützt, funktionieren nur, wenn Ihre ASP.NET-Anwendung auf IIS 7,0 oder höher gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="98d7e-104">This element and the feature it supports only work if your ASP.NET application is hosted on IIS 7.0 or later versions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<applicationPool>**  
  
## <a name="syntax"></a><span data-ttu-id="98d7e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="98d7e-105">Syntax</span></span>  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98d7e-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="98d7e-106">Attributes and Elements</span></span>  

<span data-ttu-id="98d7e-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="98d7e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98d7e-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="98d7e-108">Attributes</span></span>  
  
|<span data-ttu-id="98d7e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="98d7e-109">Attribute</span></span>|<span data-ttu-id="98d7e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98d7e-110">Description</span></span>|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|<span data-ttu-id="98d7e-111">Gibt an, wie viele gleichzeitige Anforderungen ASP.net pro CPU zulässt.</span><span class="sxs-lookup"><span data-stu-id="98d7e-111">Specifies how many simultaneous requests ASP.NET allows per CPU.</span></span>|  
|`maxConcurrentThreadsPerCPU`|<span data-ttu-id="98d7e-112">Gibt an, wie viele gleichzeitige Threads für einen Anwendungs Pool für jede CPU ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="98d7e-112">Specifies how many simultaneous threads can be running for an application pool for each CPU.</span></span> <span data-ttu-id="98d7e-113">Dies bietet eine alternative Möglichkeit zum Steuern der ASP.net-Parallelität, da Sie die Anzahl verwalteter Threads, die pro CPU verwendet werden können, für die Verarbeitung von Anforderungen einschränken können.</span><span class="sxs-lookup"><span data-stu-id="98d7e-113">This provides an alternative way to control ASP.NET concurrency, because you can limit the number of managed threads that can be used per CPU to serve requests.</span></span> <span data-ttu-id="98d7e-114">Diese Einstellung ist standardmäßig auf 0 festgelegt. Dies bedeutet, dass ASP.net die Anzahl der Threads, die pro CPU erstellt werden können, nicht einschränkt, obwohl der CLR-Thread Pool auch die Anzahl der Threads einschränkt, die erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="98d7e-114">By default this setting is 0, which means that ASP.NET does not limit the number of threads that can be created per CPU, although the CLR thread pool also limits the number of threads that can be created.</span></span>|  
|`requestQueueLimit`|<span data-ttu-id="98d7e-115">Gibt die maximale Anzahl von Anforderungen an, die in einem einzelnen Prozess in eine Warteschlange eingereiht werden können.</span><span class="sxs-lookup"><span data-stu-id="98d7e-115">Specifies the maximum number of requests that can be queued for ASP.NET in a single process.</span></span> <span data-ttu-id="98d7e-116">Wenn mindestens zwei ASP.NET-Anwendungen in einem einzelnen Anwendungs Pool ausgeführt werden, unterliegt der kumulative Satz von Anforderungen, die an eine beliebige Anwendung im Anwendungs Pool vorgenommen werden, dieser Einstellung.</span><span class="sxs-lookup"><span data-stu-id="98d7e-116">When two or more ASP.NET applications run in a single application pool, the cumulative set of requests being made to any application in the application pool is subject to this setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98d7e-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="98d7e-117">Child Elements</span></span>  

 <span data-ttu-id="98d7e-118">Keine</span><span class="sxs-lookup"><span data-stu-id="98d7e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98d7e-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="98d7e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="98d7e-120">Element</span><span class="sxs-lookup"><span data-stu-id="98d7e-120">Element</span></span>|<span data-ttu-id="98d7e-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98d7e-121">Description</span></span>|  
|-------------|-----------------|  
|[\<system.web>](system-web-element-web-settings.md)|<span data-ttu-id="98d7e-122">Enthält Informationen dazu, wie ASP.net mit einer Host Anwendung interagiert.</span><span class="sxs-lookup"><span data-stu-id="98d7e-122">Contains information about how ASP.NET interacts with a host application.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98d7e-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="98d7e-123">Remarks</span></span>  

<span data-ttu-id="98d7e-124">Wenn Sie IIS 7,0 oder eine höhere Version im integrierten Modus ausführen, können Sie mit dieser Element Kombination konfigurieren, wie ASP.NET Threads und Warteschlangen Anforderungen verwaltet, wenn die Anwendung in einem IIS-Anwendungs Pool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="98d7e-124">When you run IIS 7.0 or a later version in Integrated mode, this element combination lets you configure how ASP.NET manages threads and queues requests when the application is hosted in an IIS application pool.</span></span> <span data-ttu-id="98d7e-125">Wenn Sie IIS 6 ausführen oder IIS 7,0 im klassischen Modus oder im ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="98d7e-125">If you run IIS 6 or you run IIS 7.0 in Classic mode or in ISAPI mode, these settings are ignored.</span></span>  
  
<span data-ttu-id="98d7e-126">Die `applicationPool` Einstellungen gelten für alle Anwendungs Pools, die auf einer bestimmten Version des .NET Framework ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="98d7e-126">The `applicationPool` settings apply to all application pools that run on a particular version of the .NET Framework.</span></span> <span data-ttu-id="98d7e-127">Die Einstellungen sind in einer aspnet.config Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="98d7e-127">The settings are contained in an aspnet.config file.</span></span> <span data-ttu-id="98d7e-128">Es gibt eine Version dieser Datei für die Versionen 2,0 und 4,0 der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="98d7e-128">There is a version of this file for versions 2.0 and 4.0 of the .NET Framework.</span></span> <span data-ttu-id="98d7e-129">(In den Versionen 3,0 und 3,5 des .NET Framework wird die aspnet.config Datei mit Version 2,0 gemeinsam genutzt.)</span><span class="sxs-lookup"><span data-stu-id="98d7e-129">(Versions 3.0 and 3.5 of the .NET Framework share the aspnet.config file with version 2.0.)</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="98d7e-130">Wenn Sie IIS 7,0 unter Windows 7 ausführen, können Sie für jeden Anwendungs Pool eine separate aspnet.config Datei konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="98d7e-130">If you run IIS 7.0 on Windows 7, you can configure a separate aspnet.config file for every application pool.</span></span> <span data-ttu-id="98d7e-131">Auf diese Weise können Sie die Leistung der Threads für jeden Anwendungs Pool anpassen.</span><span class="sxs-lookup"><span data-stu-id="98d7e-131">This lets you tailor the performance of the threads for each application pool.</span></span>  
  
<span data-ttu-id="98d7e-132">Bei der `maxConcurrentRequestsPerCPU` Einstellung deaktiviert die Standardeinstellung "5000" in der .NET Framework 4 effektiv die Anforderungs Drosselung, die von ASP.net gesteuert wird, es sei denn, Sie haben tatsächlich 5000 oder mehr Anforderungen pro CPU.</span><span class="sxs-lookup"><span data-stu-id="98d7e-132">For the `maxConcurrentRequestsPerCPU` setting, the default setting of "5000" in the .NET Framework 4 effectively turns off request throttling that is controlled by ASP.NET, unless you actually have 5000 or more requests per CPU.</span></span> <span data-ttu-id="98d7e-133">Die Standardeinstellung hängt stattdessen vom CLR-Thread Pool ab, um Parallelität pro CPU automatisch zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="98d7e-133">The default setting depends instead on the CLR thread-pool to automatically manage concurrency per CPU.</span></span> <span data-ttu-id="98d7e-134">Anwendungen, die eine umfangreiche Verwendung asynchroner Anforderungs Verarbeitung oder viele Anforderungen mit langer Ausführungszeit in Netzwerk-e/a blockieren, profitieren von der erhöhten Standardgrenze in der .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="98d7e-134">Applications that make extensive use of asynchronous request processing, or that have many long-running requests blocked on network I/O, will benefit from the increased default limit in the .NET Framework 4.</span></span> <span data-ttu-id="98d7e-135">`maxConcurrentRequestsPerCPU`Wenn Sie auf NULL festlegen, wird die Verwendung verwalteter Threads für die Verarbeitung von ASP.NET-Anforderungen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="98d7e-135">Setting `maxConcurrentRequestsPerCPU` to zero turns off the use of managed threads for processing ASP.NET requests.</span></span> <span data-ttu-id="98d7e-136">Wenn eine Anwendung in einem IIS-Anwendungs Pool ausgeführt wird, bleiben Anforderungen im IIS-e/a-Thread erhalten. Daher wird die Parallelität durch IIS-Thread Einstellungen gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="98d7e-136">When an application runs in an IIS application pool, requests stay on the IIS I/O thread and therefore concurrency is throttled by IIS thread settings.</span></span>  
  
<span data-ttu-id="98d7e-137">Die- `requestQueueLimit` Einstellung funktioniert genauso wie das- `requestQueueLimit` Attribut des [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) -Elements, das in den Web.config Dateien für ASP.NET-Anwendungen festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="98d7e-137">The `requestQueueLimit` setting works the same way as the `requestQueueLimit` attribute of the [processModel](/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) element, which is set in the Web.config files for ASP.NET applications.</span></span> <span data-ttu-id="98d7e-138">Die- `requestQueueLimit` Einstellung in einer aspnet.config Datei überschreibt jedoch die- `requestQueueLimit` Einstellung in einer Web.config Datei.</span><span class="sxs-lookup"><span data-stu-id="98d7e-138">However, the `requestQueueLimit` setting in an aspnet.config file overrides the `requestQueueLimit` setting in a Web.config file.</span></span> <span data-ttu-id="98d7e-139">Anders ausgedrückt: Wenn beide Attribute festgelegt sind (Standardmäßig ist dies true), hat die `requestQueueLimit` Einstellung in der aspnet.config Datei Vorrang.</span><span class="sxs-lookup"><span data-stu-id="98d7e-139">In other words, if both attributes are set (by default, this is true), the `requestQueueLimit` setting in the aspnet.config file takes precedence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98d7e-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98d7e-140">Example</span></span>  

<span data-ttu-id="98d7e-141">Im folgenden Beispiel wird gezeigt, wie Sie das Prozess weite Verhalten von ASP.net in der aspnet.config-Datei in folgenden Situationen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="98d7e-141">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file in the following circumstances:</span></span>  
  
- <span data-ttu-id="98d7e-142">Die Anwendung wird in einem IIS 7,0-Anwendungs Pool gehostet.</span><span class="sxs-lookup"><span data-stu-id="98d7e-142">The application is hosted in an IIS 7.0 application pool.</span></span>  
  
- <span data-ttu-id="98d7e-143">IIS 7,0 wird im integrierten Modus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98d7e-143">IIS 7.0 is running in Integrated mode.</span></span>  
  
- <span data-ttu-id="98d7e-144">Die Anwendung verwendet den .NET Framework 3,5 SP1 oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="98d7e-144">The application is using the .NET Framework 3.5 SP1 or a later version.</span></span>  
  
<span data-ttu-id="98d7e-145">Bei den Werten im Beispiel handelt es sich um die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="98d7e-145">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="98d7e-146">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="98d7e-146">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98d7e-147">Namespace</span><span class="sxs-lookup"><span data-stu-id="98d7e-147">Namespace</span></span>||  
|<span data-ttu-id="98d7e-148">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="98d7e-148">Schema Name</span></span>||  
|<span data-ttu-id="98d7e-149">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="98d7e-149">Validation File</span></span>||  
|<span data-ttu-id="98d7e-150">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="98d7e-150">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="98d7e-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98d7e-151">See also</span></span>

- [<span data-ttu-id="98d7e-152">\<system.web> -Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="98d7e-152">\<system.web> Element (Web Settings)</span></span>](system-web-element-web-settings.md)
