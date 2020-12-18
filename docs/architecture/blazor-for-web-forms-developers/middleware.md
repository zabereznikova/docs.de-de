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
# <a name="modules-handlers-and-middleware"></a>Module, Handler und Middleware

Eine ASP.net Core-App basiert auf einer Reihe von *Middleware*. Middleware ist Handler, die in einer Pipeline angeordnet sind, um Anforderungen und Antworten zu verarbeiten. In einer Web Forms-App lösen HTTP-Handler und-Module ähnliche Probleme aus. In ASP.net Core werden Module, Handler, *Global.asax.cs* und der Lebenszyklus der app durch Middleware ersetzt. In diesem Kapitel erfahren Sie mehr über Middleware im Kontext einer- Blazor app.

## <a name="overview"></a>Übersicht

Die ASP.NET Core-Anforderungspipeline besteht aus einer Sequenz von Anforderungsdelegaten, die nacheinander aufgerufen werden. Das Konzept wird im folgenden Diagramm veranschaulicht. Der Ausführungsthread folgt den schwarzen Pfeilen.

![pipeline](media/middleware/request-delegate-pipeline.png)

Im vorangehenden Diagramm fehlt ein Konzept von Lebenszyklus Ereignissen. Dieses Konzept ist grundlegend für die Behandlung von ASP.net-Web Forms Anforderungen. Dieses System erleichtert das Auftreten des Vorgangs und ermöglicht das Einfügen von Middleware zu jedem beliebigen Zeitpunkt. Die Middleware wird in der Reihenfolge ausgeführt, in der Sie der Anforderungs Pipeline hinzugefügt wird. Sie werden auch im Code anstelle von Konfigurationsdateien hinzugefügt, normalerweise in *Startup.cs*.

## <a name="katana"></a>Katana

Leser, die mit Katana vertraut sind, werden sich in ASP.net Core fühlen. In der Tat ist Katana ein Framework, von dem ASP.net Core abgeleitet ist. Es wurde eine ähnliche Middleware und Pipeline Muster für ASP.NET 4. x eingeführt. Die für Katana entworfene Middleware kann an die ASP.net Core Pipeline angepasst werden.

## <a name="common-middleware"></a>Allgemeine Middleware

ASP.NET 4. x umfasst viele Module. In ähnlicher Weise verfügt ASP.net Core auch über zahlreiche middlewarekomponenten. IIS-Module können in einigen Fällen mit ASP.net Core verwendet werden. In anderen Fällen ist möglicherweise die systemeigene ASP.net Core Middleware verfügbar.

In der folgenden Tabelle werden die Ersetzungs Middleware und Komponenten in ASP.net Core aufgelistet.

|Modul                 |ASP.NET 4. x-Modul           |ASP.net Core Option|
|-----------------------|-----------------------------|-------------------|
|HTTP-Fehler            |`CustomErrorModule`          |[Middleware für Statuscodeseiten](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|Standarddokument       |`DefaultDocumentModule`      |[Middleware für Standarddateien](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|Verzeichnissuche     |`DirectoryListingModule`     |[Middleware für Verzeichnissuche](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|Dynamische Komprimierung    |`DynamicCompressionModule`   |[Antworten komprimierende Middleware](/aspnet/core/performance/response-compression)|
|Ablauf Verfolgung für Anforderungs Fehler|`FailedRequestsTracingModule`|[ASP.NET Core-Protokollierung](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|Zwischenspeichern von Dateien           |`FileCacheModule`            |[Antworten zwischenspeichernde Middleware](/aspnet/core/performance/caching/middleware)|
|HTTP-Caching           |`HttpCacheModule`            |[Antworten zwischenspeichernde Middleware](/aspnet/core/performance/caching/middleware)|
|HTTP-Protokollierung           |`HttpLoggingModule`          |[ASP.NET Core-Protokollierung](/aspnet/core/fundamentals/logging/index)|
|HTTP-Umleitung       |`HttpRedirectionModule`      |[URL-umschreibende Middleware](/aspnet/core/fundamentals/url-rewriting)|
|ISAPI-Filter          |`IsapiFilterModule`          |[Middleware](/aspnet/core/fundamentals/middleware/index)|
|ISAPI                  |`IsapiModule`                |[Middleware](/aspnet/core/fundamentals/middleware/index)|
|Anforderungsfilterung      |`RequestFilteringModule`     |[URL-Umschreib Ende Middleware-iRule](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|URL-Umschreib&#8224;   |`RewriteModule`              |[URL-umschreibende Middleware](/aspnet/core/fundamentals/url-rewriting)|
|Statische Komprimierung     |`StaticCompressionModule`    |[Antworten komprimierende Middleware](/aspnet/core/performance/response-compression)|
|Statischer Inhalt         |`StaticFileModule`           |[Middleware für statische Dateien](/aspnet/core/fundamentals/static-files)|
|URL-Autorisierung      |`UrlAuthorizationModule`     |[ASP.NET Core-Identität](/aspnet/core/security/authentication/identity)|

Diese Liste ist nicht vollständig, sollte jedoch eine Vorstellung davon haben, welche Zuordnung zwischen den beiden Frameworks vorhanden ist. Eine ausführlichere Liste finden Sie unter [IIS-Module mit ASP.net Core](/aspnet/core/host-and-deploy/iis/modules).

## <a name="custom-middleware"></a>Benutzerdefinierte Middleware

Integrierte Middleware verarbeitet möglicherweise nicht alle Szenarien, die für eine APP erforderlich sind. In solchen Fällen ist es sinnvoll, eine eigene Middleware zu erstellen. Es gibt mehrere Methoden zum Definieren von Middleware, bei denen es sich am einfachsten um einen einfachen Delegaten handelt. Beachten Sie die folgende Middleware, die eine Kultur Anforderung aus einer Abfrage Zeichenfolge akzeptiert:

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

Middleware kann auch als Klasse definiert werden, indem entweder die- `IMiddleware` Schnittstelle oder die folgende Middleware-Konvention implementiert wird. Weitere Informationen finden Sie unter [Schreiben von benutzerdefinierten ASP.net Core Middleware](/aspnet/core/fundamentals/middleware/write).

>[!div class="step-by-step"]
>[Zurück](data.md)
>[Weiter](config.md)
