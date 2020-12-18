---
title: Module, Handler und Middleware
description: Erfahren Sie mehr über die Verarbeitung von HTTP-Anforderungen mit Modulen, Handlern und Middleware.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 10/11/2019
ms.openlocfilehash: dbb0a94b0401d58139c024fd8ca3e00353a19efa
ms.sourcegitcommit: 4b79862c5b41fbd86cf38f926f6a49516059f6f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2020
ms.locfileid: "97678035"
---
# <a name="modules-handlers-and-middleware"></a><span data-ttu-id="ad27f-103">Module, Handler und Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-103">Modules, handlers, and middleware</span></span>

<span data-ttu-id="ad27f-104">Eine ASP.net Core-App basiert auf einer Reihe von *Middleware*.</span><span class="sxs-lookup"><span data-stu-id="ad27f-104">An ASP.NET Core app is built upon a series of *middleware*.</span></span> <span data-ttu-id="ad27f-105">Middleware ist Handler, die in einer Pipeline angeordnet sind, um Anforderungen und Antworten zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad27f-105">Middleware is handlers that are arranged into a pipeline to handle requests and responses.</span></span> <span data-ttu-id="ad27f-106">In einer Web Forms-App lösen HTTP-Handler und-Module ähnliche Probleme aus.</span><span class="sxs-lookup"><span data-stu-id="ad27f-106">In a Web Forms app, HTTP handlers and modules solve similar problems.</span></span> <span data-ttu-id="ad27f-107">In ASP.net Core werden Module, Handler, *Global.asax.cs* und der Lebenszyklus der app durch Middleware ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ad27f-107">In ASP.NET Core, modules, handlers, *Global.asax.cs*, and the app life cycle are replaced with middleware.</span></span> <span data-ttu-id="ad27f-108">In diesem Kapitel erfahren Sie mehr über Middleware im Kontext einer- Blazor app.</span><span class="sxs-lookup"><span data-stu-id="ad27f-108">In this chapter, you'll learn about middleware in the context of a Blazor app.</span></span>

## <a name="overview"></a><span data-ttu-id="ad27f-109">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ad27f-109">Overview</span></span>

<span data-ttu-id="ad27f-110">Die ASP.NET Core-Anforderungspipeline besteht aus einer Sequenz von Anforderungsdelegaten, die nacheinander aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ad27f-110">The ASP.NET Core request pipeline consists of a sequence of request delegates, called one after the other.</span></span> <span data-ttu-id="ad27f-111">Das Konzept wird im folgenden Diagramm veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ad27f-111">The following diagram demonstrates the concept.</span></span> <span data-ttu-id="ad27f-112">Der Ausführungsthread folgt den schwarzen Pfeilen.</span><span class="sxs-lookup"><span data-stu-id="ad27f-112">The thread of execution follows the black arrows.</span></span>

![pipeline](media/middleware/request-delegate-pipeline.png)

<span data-ttu-id="ad27f-114">Im vorangehenden Diagramm fehlt ein Konzept von Lebenszyklus Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="ad27f-114">The preceding diagram lacks a concept of lifecycle events.</span></span> <span data-ttu-id="ad27f-115">Dieses Konzept ist grundlegend für die Behandlung von ASP.net-Web Forms Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="ad27f-115">This concept is foundational to how ASP.NET Web Forms requests are handled.</span></span> <span data-ttu-id="ad27f-116">Dieses System erleichtert das Auftreten des Vorgangs und ermöglicht das Einfügen von Middleware zu jedem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="ad27f-116">This system makes it easier to reason about what process is occurring and allows middleware to be inserted at any point.</span></span> <span data-ttu-id="ad27f-117">Die Middleware wird in der Reihenfolge ausgeführt, in der Sie der Anforderungs Pipeline hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ad27f-117">Middleware executes in the order in which it's added to the request pipeline.</span></span> <span data-ttu-id="ad27f-118">Sie werden auch im Code anstelle von Konfigurationsdateien hinzugefügt, normalerweise in *Startup.cs*.</span><span class="sxs-lookup"><span data-stu-id="ad27f-118">They're also added in code instead of configuration files, usually in *Startup.cs*.</span></span>

## <a name="katana"></a><span data-ttu-id="ad27f-119">Katana</span><span class="sxs-lookup"><span data-stu-id="ad27f-119">Katana</span></span>

<span data-ttu-id="ad27f-120">Leser, die mit Katana vertraut sind, werden sich in ASP.net Core fühlen.</span><span class="sxs-lookup"><span data-stu-id="ad27f-120">Readers familiar with Katana will feel comfortable in ASP.NET Core.</span></span> <span data-ttu-id="ad27f-121">In der Tat ist Katana ein Framework, von dem ASP.net Core abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="ad27f-121">In fact, Katana is a framework from which ASP.NET Core derives.</span></span> <span data-ttu-id="ad27f-122">Es wurde eine ähnliche Middleware und Pipeline Muster für ASP.NET 4. x eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ad27f-122">It introduced similar middleware and pipeline patterns for ASP.NET 4.x.</span></span> <span data-ttu-id="ad27f-123">Die für Katana entworfene Middleware kann an die ASP.net Core Pipeline angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="ad27f-123">Middleware designed for Katana can be adapted to work with the ASP.NET Core pipeline.</span></span>

## <a name="common-middleware"></a><span data-ttu-id="ad27f-124">Allgemeine Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-124">Common middleware</span></span>

<span data-ttu-id="ad27f-125">ASP.NET 4. x umfasst viele Module.</span><span class="sxs-lookup"><span data-stu-id="ad27f-125">ASP.NET 4.x includes many modules.</span></span> <span data-ttu-id="ad27f-126">In ähnlicher Weise verfügt ASP.net Core auch über zahlreiche middlewarekomponenten.</span><span class="sxs-lookup"><span data-stu-id="ad27f-126">In a similar fashion, ASP.NET Core has many middleware components available as well.</span></span> <span data-ttu-id="ad27f-127">IIS-Module können in einigen Fällen mit ASP.net Core verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad27f-127">IIS modules may be used in some cases with ASP.NET Core.</span></span> <span data-ttu-id="ad27f-128">In anderen Fällen ist möglicherweise die systemeigene ASP.net Core Middleware verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ad27f-128">In other cases, native ASP.NET Core middleware may be available.</span></span>

<span data-ttu-id="ad27f-129">In der folgenden Tabelle werden die Ersetzungs Middleware und Komponenten in ASP.net Core aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ad27f-129">The following table lists replacement middleware and components in ASP.NET Core.</span></span>

|<span data-ttu-id="ad27f-130">Modul</span><span class="sxs-lookup"><span data-stu-id="ad27f-130">Module</span></span>                 |<span data-ttu-id="ad27f-131">ASP.NET 4. x-Modul</span><span class="sxs-lookup"><span data-stu-id="ad27f-131">ASP.NET 4.x module</span></span>           |<span data-ttu-id="ad27f-132">ASP.net Core Option</span><span class="sxs-lookup"><span data-stu-id="ad27f-132">ASP.NET Core option</span></span>|
|-----------------------|-----------------------------|-------------------|
|<span data-ttu-id="ad27f-133">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="ad27f-133">HTTP errors</span></span>            |`CustomErrorModule`          |[<span data-ttu-id="ad27f-134">Middleware für Statuscodeseiten</span><span class="sxs-lookup"><span data-stu-id="ad27f-134">Status Code Pages Middleware</span></span>](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|<span data-ttu-id="ad27f-135">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="ad27f-135">Default document</span></span>       |`DefaultDocumentModule`      |[<span data-ttu-id="ad27f-136">Middleware für Standarddateien</span><span class="sxs-lookup"><span data-stu-id="ad27f-136">Default Files Middleware</span></span>](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|<span data-ttu-id="ad27f-137">Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="ad27f-137">Directory browsing</span></span>     |`DirectoryListingModule`     |[<span data-ttu-id="ad27f-138">Middleware für Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="ad27f-138">Directory Browsing Middleware</span></span>](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|<span data-ttu-id="ad27f-139">Dynamische Komprimierung</span><span class="sxs-lookup"><span data-stu-id="ad27f-139">Dynamic compression</span></span>    |`DynamicCompressionModule`   |[<span data-ttu-id="ad27f-140">Antworten komprimierende Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-140">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="ad27f-141">Ablauf Verfolgung für Anforderungs Fehler</span><span class="sxs-lookup"><span data-stu-id="ad27f-141">Failed requests tracing</span></span>|`FailedRequestsTracingModule`|[<span data-ttu-id="ad27f-142">ASP.NET Core-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="ad27f-142">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|<span data-ttu-id="ad27f-143">Zwischenspeichern von Dateien</span><span class="sxs-lookup"><span data-stu-id="ad27f-143">File caching</span></span>           |`FileCacheModule`            |[<span data-ttu-id="ad27f-144">Antworten zwischenspeichernde Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-144">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="ad27f-145">HTTP-Caching</span><span class="sxs-lookup"><span data-stu-id="ad27f-145">HTTP caching</span></span>           |`HttpCacheModule`            |[<span data-ttu-id="ad27f-146">Antworten zwischenspeichernde Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-146">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="ad27f-147">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="ad27f-147">HTTP logging</span></span>           |`HttpLoggingModule`          |[<span data-ttu-id="ad27f-148">ASP.NET Core-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="ad27f-148">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index)|
|<span data-ttu-id="ad27f-149">HTTP-Umleitung</span><span class="sxs-lookup"><span data-stu-id="ad27f-149">HTTP redirection</span></span>       |`HttpRedirectionModule`      |[<span data-ttu-id="ad27f-150">URL-umschreibende Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-150">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="ad27f-151">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="ad27f-151">ISAPI filters</span></span>          |`IsapiFilterModule`          |[<span data-ttu-id="ad27f-152">Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-152">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="ad27f-153">ISAPI</span><span class="sxs-lookup"><span data-stu-id="ad27f-153">ISAPI</span></span>                  |`IsapiModule`                |[<span data-ttu-id="ad27f-154">Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-154">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="ad27f-155">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="ad27f-155">Request filtering</span></span>      |`RequestFilteringModule`     |[<span data-ttu-id="ad27f-156">URL-Umschreib Ende Middleware-iRule</span><span class="sxs-lookup"><span data-stu-id="ad27f-156">URL Rewriting Middleware IRule</span></span>](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|<span data-ttu-id="ad27f-157">URL-Umschreib&#8224;</span><span class="sxs-lookup"><span data-stu-id="ad27f-157">URL rewriting&#8224;</span></span>   |`RewriteModule`              |[<span data-ttu-id="ad27f-158">URL-umschreibende Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-158">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="ad27f-159">Statische Komprimierung</span><span class="sxs-lookup"><span data-stu-id="ad27f-159">Static compression</span></span>     |`StaticCompressionModule`    |[<span data-ttu-id="ad27f-160">Antworten komprimierende Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-160">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="ad27f-161">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="ad27f-161">Static content</span></span>         |`StaticFileModule`           |[<span data-ttu-id="ad27f-162">Middleware für statische Dateien</span><span class="sxs-lookup"><span data-stu-id="ad27f-162">Static File Middleware</span></span>](/aspnet/core/fundamentals/static-files)|
|<span data-ttu-id="ad27f-163">URL-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="ad27f-163">URL authorization</span></span>      |`UrlAuthorizationModule`     |[<span data-ttu-id="ad27f-164">ASP.NET Core-Identität</span><span class="sxs-lookup"><span data-stu-id="ad27f-164">ASP.NET Core Identity</span></span>](/aspnet/core/security/authentication/identity)|

<span data-ttu-id="ad27f-165">Diese Liste ist nicht vollständig, sollte jedoch eine Vorstellung davon haben, welche Zuordnung zwischen den beiden Frameworks vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ad27f-165">This list isn't exhaustive but should give an idea of what mapping exists between the two frameworks.</span></span> <span data-ttu-id="ad27f-166">Eine ausführlichere Liste finden Sie unter [IIS-Module mit ASP.net Core](/aspnet/core/host-and-deploy/iis/modules).</span><span class="sxs-lookup"><span data-stu-id="ad27f-166">For a more detailed list, see [IIS modules with ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span></span>

## <a name="custom-middleware"></a><span data-ttu-id="ad27f-167">Benutzerdefinierte Middleware</span><span class="sxs-lookup"><span data-stu-id="ad27f-167">Custom middleware</span></span>

<span data-ttu-id="ad27f-168">Integrierte Middleware verarbeitet möglicherweise nicht alle Szenarien, die für eine APP erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ad27f-168">Built-in middleware may not handle all scenarios needed for an app.</span></span> <span data-ttu-id="ad27f-169">In solchen Fällen ist es sinnvoll, eine eigene Middleware zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad27f-169">In such cases, it makes sense to create your own middleware.</span></span> <span data-ttu-id="ad27f-170">Es gibt mehrere Methoden zum Definieren von Middleware, bei denen es sich am einfachsten um einen einfachen Delegaten handelt.</span><span class="sxs-lookup"><span data-stu-id="ad27f-170">There are multiple ways of defining middleware, with the simplest being a simple delegate.</span></span> <span data-ttu-id="ad27f-171">Beachten Sie die folgende Middleware, die eine Kultur Anforderung aus einer Abfrage Zeichenfolge akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="ad27f-171">Consider the following middleware, which accepts a culture request from a query string:</span></span>

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

<span data-ttu-id="ad27f-172">Middleware kann auch als Klasse definiert werden, indem entweder die- `IMiddleware` Schnittstelle oder die folgende Middleware-Konvention implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ad27f-172">Middleware can also be defined as class, either by implementing the `IMiddleware` interface or by following middleware convention.</span></span> <span data-ttu-id="ad27f-173">Weitere Informationen finden Sie unter [Schreiben von benutzerdefinierten ASP.net Core Middleware](/aspnet/core/fundamentals/middleware/write).</span><span class="sxs-lookup"><span data-stu-id="ad27f-173">For more information, see [Write custom ASP.NET Core middleware](/aspnet/core/fundamentals/middleware/write).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ad27f-174">[Zurück](data.md)
>[Weiter](config.md)</span><span class="sxs-lookup"><span data-stu-id="ad27f-174">[Previous](data.md)
[Next](config.md)</span></span>
