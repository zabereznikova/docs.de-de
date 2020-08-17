---
title: App-Start
description: Erfahren Sie, wie Sie die Start Logik für Ihre APP definieren.
author: csharpfritz
ms.author: jefritz
ms.date: 02/25/2020
ms.openlocfilehash: ea2ea458011d8351a834aa12db02e5d2bac2dc65
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267697"
---
# <a name="app-startup"></a>App-Start

Anwendungen, die für ASP.NET geschrieben werden, verfügen in der Regel über eine `global.asax.cs` Datei, in der das `Application_Start` Ereignis definiert ist, das steuert, welche Dienste für HTML-Rendering und .NET-Verarbeitung zur Verfügung gestellt werden. In diesem Kapitel wird erläutert, wie sich die Dinge bei ASP.net Core-und blazor-Server geringfügig unterscheiden.

## <a name="application_start-and-web-forms"></a>Application_Start und Web Forms

Die standardmäßige Web Forms- `Application_Start` Methode wurde im Laufe der Zeit über Jahre erweitert, um viele Konfigurationsaufgaben zu verarbeiten.  Ein neues Web Forms-Projekt mit der Standardvorlage in Visual Studio 2019 enthält jetzt die folgende Konfigurations Logik:

- `RouteConfig` -Anwendungs-URL-Routing
- `BundleConfig` -CSS und JavaScript-Bündelung und-Minimierung

Jede dieser einzelnen Dateien befindet sich im `App_Start` Ordner und wird nur einmal am Anfang der Anwendung ausgeführt.  `RouteConfig` Fügt in der Standard Projektvorlage den `FriendlyUrlSettings` für Web Forms hinzu, damit Anwendungs-URLs die Dateierweiterung weglassen können `.ASPX` .  Die Standardvorlage enthält auch eine-Direktive, die permanente http-Umleitungs Statuscodes (http 301) für die `.ASPX` Seiten an die Friendly URL mit dem Dateinamen bereitstellt, der die Erweiterung auslässt.

Mit ASP.net Core und blazor werden diese Methoden entweder vereinfacht und in der-Klasse konsolidiert, `Startup` oder Sie werden zugunsten gängiger Webtechnologien eliminiert.

## <a name="blazor-server-startup-structure"></a>Start Struktur des blazor-Servers

Blazor-Server Anwendungen befinden sich auf einem ASP.net Core 3,0 oder einer höheren Anwendung.  ASP.net Core Webanwendungen werden über ein paar von Methoden in der-Klasse im Stamm `Startup.cs` Ordner der Anwendung konfiguriert.  Der Standard Inhalt der Startklasse ist unten aufgeführt.

```csharp
public class Startup
{
  public Startup(IConfiguration configuration)
  {
    Configuration = configuration;
  }

  public IConfiguration Configuration { get; }

  // This method gets called by the runtime. Use this method to add services to the container.
  // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
  public void ConfigureServices(IServiceCollection services)
  {
    services.AddRazorPages();
    services.AddServerSideBlazor();
    services.AddSingleton<WeatherForecastService>();
  }

  // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
  public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
  {
    if (env.IsDevelopment())
    {
      app.UseDeveloperExceptionPage();
    }
    else
    {
      app.UseExceptionHandler("/Error");
      // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
      app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
      endpoints.MapBlazorHub();
      endpoints.MapFallbackToPage("/_Host");
   });
  }
 }
```

Wie bei den restlichen ASP.net Core wird die Startup-Klasse mit den Prinzipien der Abhängigkeitsinjektion erstellt.  `IConfiguration`Wird für den Konstruktor bereitgestellt und für den späteren Zugriff während der Konfiguration in einer öffentlichen Eigenschaft gezischt.

Die `ConfigureServices` in ASP.net Core eingeführte-Methode ermöglicht die Konfiguration der verschiedenen ASP.net Core Framework-Dienste für den integrierten Abhängigkeits Injection-Container des Frameworks.  Mit den verschiedenen `services.Add*` Methoden werden Dienste hinzugefügt, die Funktionen wie Authentifizierung, Razor-Seiten, MVC-Controller Routing, signalr-und blazor-Server Interaktionen unter vielen anderen Funktionen ermöglichen.  Diese Methode wurde in Web Forms nicht benötigt, da die Verarbeitung und Behandlung der ASPX-, ASCX-, ashx-und ASMX-Dateien durch Verweisen auf ASP.net in der web.config Konfigurationsdatei definiert wurde.  Weitere Informationen zur Abhängigkeitsinjektion in ASP.net Core finden Sie in der [Online Dokumentation](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).

Mit der- `Configure` Methode wird das Konzept der HTTP-Pipeline zum ASP.net Core eingeführt.  Bei dieser Methode deklarieren wir von oben nach unten die [Middleware](middleware.md) , die jede Anforderung verarbeitet, die an die Anwendung gesendet wird. Die meisten dieser Features in der Standardkonfiguration waren in den Web Forms-Konfigurationsdateien verstreut und sind nun an einem Ort, um die Referenz zu vereinfachen.

Die Konfiguration der benutzerdefinierten Fehlerseite ist nicht mehr in einer `web.config` Datei gespeichert, sondern ist nun so konfiguriert, dass Sie immer angezeigt wird, wenn die Anwendungsumgebung nicht beschriftet ist `Development` .  Darüber hinaus sind ASP.net Core Anwendungen nun so konfiguriert, dass Sie sichere Seiten mit TLS standardmäßig mit dem-Methoden Befehl bereitstellen `UseHttpsRedirection` .

Als nächstes wird eine unerwartete Konfigurations Methode in aufgelistet `UseStaticFiles` .  In ASP.net Core muss die Unterstützung für statische Dateien (z. b. JavaScript-, CSS-und Bilddateien) explizit aktiviert werden, und nur die Dateien im Ordner " *wwwroot* " der APP sind standardmäßig öffentlich adressierbar.

Die nächste Zeile ist die erste Zeile, in der eine der Konfigurationsoptionen von Web Forms repliziert wird: `UseRouting` .  Diese Methode fügt der Pipeline den ASP.net Core Router hinzu, und er kann entweder hier oder in den einzelnen Dateien konfiguriert werden, an die er weiterleiten kann.  Weitere Informationen zur Routing Konfiguration finden Sie im [Abschnitt Routing](pages-routing-layouts.md).

Die letzte Anweisung in dieser Methode definiert die Endpunkte, die ASP.net Core überwachen.  Dabei handelt es sich um Websites, auf die über den Webserver zugegriffen werden kann, auf die Sie auf dem Webserver zugreifen und Inhalte erhalten, die von .NET verarbeitet und an Sie  Der erste Eintrag `MapBlazorHub` konfiguriert einen signalr-Hub für die Verwendung bei der Bereitstellung der Echtzeitverbindung und der permanenten Verbindung mit dem Server, auf dem der Status und das Rendering von blazor-Komponenten behandelt werden.  Der `MapFallbackToPage` Methodenaufruf gibt den Speicherort der Website an, auf die der Zugriff auf die Seite der Seite erfolgt, von der die blazor-Anwendung gestartet wird. Außerdem wird die Anwendung für die Verarbeitung von Deep-Linking-Anforderungen von Client  Diese Funktion wird bei der Arbeit angezeigt, wenn Sie einen Browser öffnen und direkt zur von blazor verarbeiteten Route in Ihrer Anwendung navigieren, z `/counter` . b. in der Standard Projektvorlage. Die Anforderung wird von der Fall Back-Seite *_Host. cshtml* verarbeitet, von der dann der blazor-Router ausgeführt und die Gegenseite gerendert wird.

## <a name="upgrading-the-bundleconfig-process"></a>Aktualisieren des bundleconfig-Prozesses

Technologien zum Bündeln von Assets wie CSS-Stylesheets und JavaScript-Dateien haben sich deutlich verbessert, mit anderen Technologien, die sich schnell entwickelnden Tools und Techniken zur Verwaltung dieser Ressourcen anbieten.  Zu diesem Zweck empfehlen wir die Verwendung eines Node-Befehlszeilen Tools, wie z. b. grunt/Gulp/WebPack, um Ihre statischen Assets zu verpacken.

Die Befehlszeilen Tools "Grunt", "Gulp" und "WebPack" und die zugehörigen Konfigurationen können Ihrer Anwendung hinzugefügt werden. diese Dateien werden von ASP.net Core während des anwendungsbuildprozesses in Ruhe ignoriert.  Sie können einen-Befehl zum Ausführen ihrer Aufgaben hinzufügen, indem Sie eine `Target` in der Projektdatei mit einer Syntax hinzufügen, die der folgenden ähnelt, die ein Gulp-Skript und das `min` Ziel innerhalb des Skripts auslöst.

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="gulp min" />
</Target>
```

Weitere Informationen zu beiden Strategien zum Verwalten Ihrer CSS-und JavaScript-Dateien finden Sie in den Paketen [und minimieren static Assets in ASP.net Core](https://docs.microsoft.com/aspnet/core/client-side/bundling-and-minification) Dokumentation.

>[!div class="step-by-step"]
>[Zurück](project-structure.md)
>[Weiter](components.md)
