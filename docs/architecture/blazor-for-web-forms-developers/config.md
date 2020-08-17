---
title: App-Konfiguration
description: Erfahren Sie, wie Sie Blazor apps ohne Verwendung von ConfigurationManager konfigurieren.
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 04/01/2020
ms.openlocfilehash: 6154b4f8c7a5bff42e603b12d5ef85468b80224e
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267502"
---
# <a name="app-configuration"></a><span data-ttu-id="649fe-103">App-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="649fe-103">App configuration</span></span>

<span data-ttu-id="649fe-104">Die primäre Methode zum Laden der APP-Konfiguration in Web Forms ist die Verwendung von Einträgen in der *web.config* Datei &mdash; auf dem Server oder einer zugehörigen Konfigurationsdatei, auf die von *web.config*verwiesen wird. Sie können das statische `ConfigurationManager` Objekt für die Interaktion mit App-Einstellungen, Datenrepository-Verbindungs Zeichenfolgen und anderen erweiterten Konfigurations Anbietern verwenden, die der app hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="649fe-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="649fe-105">Es ist üblich, Interaktionen mit der APP-Konfiguration wie im folgenden Code zu sehen:</span><span class="sxs-lookup"><span data-stu-id="649fe-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="649fe-106">BlazorWenn *web.config* die APP auf einem Windows IIS-Server gehostet wird, kann ASP.net Core und serverseitig vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="649fe-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="649fe-107">Es gibt jedoch keine `ConfigurationManager` Interaktion mit dieser Konfiguration, und Sie können eine strukturiertere App-Konfiguration aus anderen Quellen erhalten.</span><span class="sxs-lookup"><span data-stu-id="649fe-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="649fe-108">Sehen wir uns nun an, wie die Konfiguration erfasst wird und wie Sie weiterhin über eine *web.config* Datei auf Konfigurationsinformationen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="649fe-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="649fe-109">Konfigurationsquellen</span><span class="sxs-lookup"><span data-stu-id="649fe-109">Configuration sources</span></span>

<span data-ttu-id="649fe-110">ASP.net Core erkennt, dass es viele Konfigurations Quellen gibt, die Sie möglicherweise für Ihre APP verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="649fe-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="649fe-111">Das Framework versucht, Ihnen standardmäßig das beste dieser Features anzubieten.</span><span class="sxs-lookup"><span data-stu-id="649fe-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="649fe-112">Die Konfiguration wird aus diesen verschiedenen Quellen durch ASP.net Core gelesen und aggregiert.</span><span class="sxs-lookup"><span data-stu-id="649fe-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="649fe-113">Später geladene Werte für denselben Konfigurationsschlüssel haben Vorrang vor früheren Werten.</span><span class="sxs-lookup"><span data-stu-id="649fe-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="649fe-114">ASP.net Core wurde in der Cloud unterstützt und erleichtert die Konfiguration von Apps für Operatoren und Entwickler.</span><span class="sxs-lookup"><span data-stu-id="649fe-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="649fe-115">ASP.net Core ist für die Umgebung von der Umgebung abhängig und weiß, ob Sie in ihrer-oder-Umgebung ausgeführt wird `Production` `Development` .</span><span class="sxs-lookup"><span data-stu-id="649fe-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="649fe-116">Der Umgebungs Indikator wird in der `ASPNETCORE_ENVIRONMENT` System Umgebungsvariablen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="649fe-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="649fe-117">Wenn kein Wert konfiguriert ist, wird die App standardmäßig in der `Production` Umgebung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="649fe-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="649fe-118">Ihre APP kann basierend auf dem Namen der Umgebung eine Konfiguration aus mehreren Quellen initiieren und hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="649fe-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="649fe-119">Standardmäßig wird die Konfiguration aus den folgenden Ressourcen in der aufgeführten Reihenfolge geladen:</span><span class="sxs-lookup"><span data-stu-id="649fe-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="649fe-120">Datei *appsettings.js* (sofern vorhanden)</span><span class="sxs-lookup"><span data-stu-id="649fe-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="649fe-121">*appSettings. {ENVIRONMENT_NAME}. JSON* -Datei, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="649fe-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="649fe-122">Benutzer Geheimnis Datei auf Datenträger, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="649fe-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="649fe-123">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="649fe-123">Environment variables</span></span>
1. <span data-ttu-id="649fe-124">Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="649fe-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="649fe-125">appsettings.jsvon Format und Zugriff</span><span class="sxs-lookup"><span data-stu-id="649fe-125">appsettings.json format and access</span></span>

<span data-ttu-id="649fe-126">Die *appsettings.jsfür* die Datei kann hierarchisch sein, wobei die Werte wie im folgenden JSON-Code strukturiert sind:</span><span class="sxs-lookup"><span data-stu-id="649fe-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

<span data-ttu-id="649fe-127">Wenn das Konfigurationssystem mit dem vorangehenden JSON-Code dargestellt wird, werden untergeordnete Werte vereinfacht und auf die voll qualifizierten hierarchischen Pfade verwiesen.</span><span class="sxs-lookup"><span data-stu-id="649fe-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="649fe-128">Ein Doppelpunkt ( `:` ) trennt jede Eigenschaft in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="649fe-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="649fe-129">Beispielsweise greift der Konfigurationsschlüssel auf `section1:key0` den `section1` Wert des Objektliterals zu `key0` .</span><span class="sxs-lookup"><span data-stu-id="649fe-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="649fe-130">Benutzer Geheimnisse</span><span class="sxs-lookup"><span data-stu-id="649fe-130">User secrets</span></span>

<span data-ttu-id="649fe-131">Benutzer Geheimnisse:</span><span class="sxs-lookup"><span data-stu-id="649fe-131">User secrets are:</span></span>

* <span data-ttu-id="649fe-132">Konfigurationswerte, die in einer JSON-Datei auf der Arbeitsstation des Entwicklers außerhalb des App-Entwicklungs Ordners gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="649fe-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="649fe-133">Wird nur geladen, wenn in der Umgebung ausgeführt wird `Development` .</span><span class="sxs-lookup"><span data-stu-id="649fe-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="649fe-134">Einer bestimmten app zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="649fe-134">Associated with a specific app.</span></span>
* <span data-ttu-id="649fe-135">Wird mit dem-Befehl des .net Core-CLI verwaltet `user-secrets` .</span><span class="sxs-lookup"><span data-stu-id="649fe-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="649fe-136">Konfigurieren Sie Ihre APP für die Speicherung von geheimen Schlüsseln durch Ausführen des folgenden `user-secrets` Befehls:</span><span class="sxs-lookup"><span data-stu-id="649fe-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="649fe-137">Mit dem vorangehenden Befehl wird `UserSecretsId` der Projektdatei ein-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="649fe-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="649fe-138">Das-Element enthält eine GUID, die verwendet wird, um Geheimnisse der APP zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="649fe-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="649fe-139">Anschließend können Sie mit dem Befehl ein Geheimnis definieren `set` .</span><span class="sxs-lookup"><span data-stu-id="649fe-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="649fe-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="649fe-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="649fe-141">Der vorherige Befehl macht den `Parent:ApiKey` Konfigurationsschlüssel auf der Arbeitsstation eines Entwicklers mit dem Wert verfügbar `12345` .</span><span class="sxs-lookup"><span data-stu-id="649fe-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="649fe-142">Weitere Informationen zum Erstellen, speichern und Verwalten von Benutzer Geheimnissen finden Sie unter [sichere Speicherung von App-Geheimnissen in der Entwicklung in ASP.net Core](/aspnet/core/security/app-secrets) Dokument.</span><span class="sxs-lookup"><span data-stu-id="649fe-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="649fe-143">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="649fe-143">Environment variables</span></span>

<span data-ttu-id="649fe-144">Die nächste Gruppe von Werten, die in Ihre APP-Konfiguration geladen werden, sind die Umgebungsvariablen des Systems.</span><span class="sxs-lookup"><span data-stu-id="649fe-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="649fe-145">Alle Umgebungsvariablen Einstellungen Ihres Systems sind nun über die Konfigurations-API zugänglich.</span><span class="sxs-lookup"><span data-stu-id="649fe-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="649fe-146">Hierarchische Werte werden vereinfacht und durch Doppelpunkte getrennt, wenn Sie in der APP gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="649fe-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="649fe-147">Allerdings lassen einige Betriebssysteme die Umgebungsvariablen Namen des Doppelpunkts nicht zu.</span><span class="sxs-lookup"><span data-stu-id="649fe-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="649fe-148">ASP.net Core adressiert diese Einschränkung, indem Werte, die doppelte Unterstriche () aufweisen, `__` beim Zugriff in einen Doppelpunkt umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="649fe-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="649fe-149">Der `Parent:ApiKey` Wert aus dem obigen Abschnitt "Benutzer Geheimnisse" kann mit der Umgebungsvariablen überschrieben werden `Parent__ApiKey` .</span><span class="sxs-lookup"><span data-stu-id="649fe-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="649fe-150">Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="649fe-150">Command-line arguments</span></span>

<span data-ttu-id="649fe-151">Die Konfiguration kann auch als Befehlszeilenargumente bereitgestellt werden, wenn Ihre APP gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="649fe-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="649fe-152">Verwenden Sie die Notation Double-Dash ( `--` ) oder Schrägstrich ( `/` ), um den Namen des festzulegenden Konfigurations Werts und den Wert anzugeben, der konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="649fe-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="649fe-153">Die Syntax ähnelt den folgenden Befehlen:</span><span class="sxs-lookup"><span data-stu-id="649fe-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="649fe-154">Die Rückgabe von web.config</span><span class="sxs-lookup"><span data-stu-id="649fe-154">The return of web.config</span></span>

<span data-ttu-id="649fe-155">Wenn Sie Ihre APP für Windows auf IIS bereitgestellt haben, konfiguriert die *web.config* Datei weiterhin IIS, um Ihre APP zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="649fe-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="649fe-156">Standardmäßig fügt IIS einen Verweis auf das ASP.net Core Modul (ancm) hinzu.</span><span class="sxs-lookup"><span data-stu-id="649fe-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="649fe-157">Bei ancm handelt es sich um ein natives IIS-Modul, das Ihre APP anstelle des Kestrel-Webservers hostet.</span><span class="sxs-lookup"><span data-stu-id="649fe-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="649fe-158">Dieser *web.config* Abschnitt ähnelt dem folgenden XML-Markup:</span><span class="sxs-lookup"><span data-stu-id="649fe-158">This *web.config* section resembles the following XML markup:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

<span data-ttu-id="649fe-159">Die APP-spezifische Konfiguration kann definiert werden, indem ein Element im-Element geschachtelt wird `environmentVariables` `aspNetCore` .</span><span class="sxs-lookup"><span data-stu-id="649fe-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="649fe-160">Die in diesem Abschnitt definierten Werte werden in der ASP.net Core-App als Umgebungsvariablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="649fe-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="649fe-161">Die Umgebungsvariablen werden während dieses Segments des App-Starts entsprechend geladen.</span><span class="sxs-lookup"><span data-stu-id="649fe-161">The environment variables load appropriately during that segment of app startup.</span></span>

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="649fe-162">Lesen der Konfiguration in der APP</span><span class="sxs-lookup"><span data-stu-id="649fe-162">Read configuration in the app</span></span>

<span data-ttu-id="649fe-163">ASP.net Core bietet die APP-Konfiguration über die- <xref:Microsoft.Extensions.Configuration.IConfiguration> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="649fe-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="649fe-164">Diese Konfigurationsschnittstelle sollte von Ihren Blazor Komponenten, Blazor Seiten und jeder anderen ASP.net Core verwalteten Klasse angefordert werden, die Zugriff auf die Konfiguration benötigt.</span><span class="sxs-lookup"><span data-stu-id="649fe-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="649fe-165">Das ASP.net Core Framework füllt diese Schnittstelle automatisch mit der zuvor konfigurierten aufgelösten Konfiguration auf.</span><span class="sxs-lookup"><span data-stu-id="649fe-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="649fe-166">Auf einer Blazor Seite oder dem Razor-Markup einer Komponente können Sie das `IConfiguration` Objekt wie folgt mit einer- `@inject` Direktive am Anfang der *Razor* -Datei einfügen:</span><span class="sxs-lookup"><span data-stu-id="649fe-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="649fe-167">Diese vorangehende Anweisung macht das `IConfiguration` Objekt in der `Configuration` gesamten Razor-Vorlage als Variable verfügbar.</span><span class="sxs-lookup"><span data-stu-id="649fe-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="649fe-168">Sie können einzelne Konfigurationseinstellungen lesen, indem Sie die Konfigurations Einstellungs Hierarchie, die als Indexer-Parameter gesucht wurde, angeben:</span><span class="sxs-lookup"><span data-stu-id="649fe-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="649fe-169">Sie können ganze Konfigurations Abschnitte abrufen, indem Sie die- <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> Methode verwenden, um eine Auflistung von Schlüsseln an einem bestimmten Speicherort mit einer ähnlichen Syntax wie zum `GetSection("section1")` Abrufen der Konfiguration für Section1 aus dem vorherigen Beispiel abzurufen.</span><span class="sxs-lookup"><span data-stu-id="649fe-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="649fe-170">Stark typisierte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="649fe-170">Strongly typed configuration</span></span>

<span data-ttu-id="649fe-171">Mit Web Forms war es möglich, einen stark typisierten Konfigurationstyp zu erstellen, der vom <xref:System.Configuration.ConfigurationSection> Typ und den zugeordneten Typen geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="649fe-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="649fe-172">`ConfigurationSection`Mit können Sie einige Geschäftsregeln und die Verarbeitung für diese Konfigurationswerte konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="649fe-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="649fe-173">In ASP.net Core können Sie eine Klassenhierarchie angeben, die die Konfigurationswerte empfängt.</span><span class="sxs-lookup"><span data-stu-id="649fe-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="649fe-174">Diese Klassen:</span><span class="sxs-lookup"><span data-stu-id="649fe-174">These classes:</span></span>

* <span data-ttu-id="649fe-175">Muss nicht von einer übergeordneten Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="649fe-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="649fe-176">Sollte `public` Eigenschaften enthalten, die mit den Eigenschaften und Typverweisen für die Konfigurations Struktur, die Sie erfassen möchten, identisch sind.</span><span class="sxs-lookup"><span data-stu-id="649fe-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="649fe-177">Für den früheren *appsettings.jszum* Beispiel könnten Sie die folgenden Klassen definieren, um die Werte zu erfassen:</span><span class="sxs-lookup"><span data-stu-id="649fe-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

<span data-ttu-id="649fe-178">Diese Klassenhierarchie kann ausgefüllt werden, indem der-Methode die folgende Zeile hinzugefügt wird `Startup.ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="649fe-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="649fe-179">Im Rest der App können Sie Klassen oder eine- `@inject` Direktive in Razor-Vorlagen des Typs einen Eingabeparameter hinzufügen, `IOptions<MyConfig>` um die stark typisierten Konfigurationseinstellungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="649fe-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="649fe-180">Die- `IOptions<MyConfig>.Value` Eigenschaft ergibt den `MyConfig` Wert, der von den Konfigurationseinstellungen aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="649fe-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="649fe-181">Weitere Informationen zu den Optionen finden Sie im [options Muster in ASP.net Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) Dokument.</span><span class="sxs-lookup"><span data-stu-id="649fe-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="649fe-182">[Zurück](middleware.md)
>[Weiter](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="649fe-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
