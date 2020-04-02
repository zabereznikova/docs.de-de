---
title: App-Konfiguration
description: Erfahren Sie, wie Sie Blazor-Apps ohne ConfigurationManager konfigurieren.
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588246"
---
# <a name="app-configuration"></a><span data-ttu-id="a3e7e-103">App-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a3e7e-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="a3e7e-104">Die primäre Möglichkeit zum Laden der App-Konfiguration in Web&mdash;Forms besteht in Einträgen in der *Datei web.config* entweder auf dem Server oder in einer zugehörigen Konfigurationsdatei, auf die von *web.config*verwiesen wird. Sie können das `ConfigurationManager` statische Objekt verwenden, um mit App-Einstellungen, Daten-Repository-Verbindungszeichenfolgen und anderen erweiterten Konfigurationsanbietern zu interagieren, die der App hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="a3e7e-105">Es ist typisch, Interaktionen mit der App-Konfiguration zu sehen, wie im folgenden Code zu sehen:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="a3e7e-106">Mit ASP.NET Core und dem serverseitigen Blazor kann die *web.config-Datei* vorhanden sein, wenn Ihre App auf einem Windows IIS-Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="a3e7e-107">Es gibt jedoch `ConfigurationManager` keine Interaktion mit dieser Konfiguration, und Sie können eine strukturiertere App-Konfiguration aus anderen Quellen erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="a3e7e-108">Werfen wir einen Blick darauf, wie die Konfiguration erfasst wird und wie Sie weiterhin über eine *web.config-Datei* auf Konfigurationsinformationen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="a3e7e-109">Konfigurationsquellen</span><span class="sxs-lookup"><span data-stu-id="a3e7e-109">Configuration sources</span></span>

<span data-ttu-id="a3e7e-110">ASP.NET Core erkennt, dass es viele Konfigurationsquellen gibt, die Sie möglicherweise für Ihre App verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="a3e7e-111">Das Framework versucht, Ihnen standardmäßig das Beste aus diesen Funktionen anzubieten.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="a3e7e-112">Die Konfiguration wird von ASP.NET Core aus diesen verschiedenen Quellen gelesen und aggregiert.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="a3e7e-113">Später geladene Werte für denselben Konfigurationsschlüssel haben Vorrang vor früheren Werten.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="a3e7e-114">ASP.NET Core wurde entwickelt, um Cloud-bewusst zu sein und die Konfiguration von Apps sowohl für Betreiber als auch für Entwickler zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="a3e7e-115">ASP.NET Core ist umgebungsbewusst und weiß, `Production` ob `Development` es in Ihrer Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="a3e7e-116">Der Umgebungsindikator wird `ASPNETCORE_ENVIRONMENT` in der Systemumgebungsvariablen gesetzt.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="a3e7e-117">Wenn kein Wert konfiguriert ist, wird die `Production` App standardmäßig in der Umgebung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="a3e7e-118">Ihre App kann die Konfiguration aus mehreren Quellen basierend auf dem Namen der Umgebung auslösen und hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="a3e7e-119">Standardmäßig wird die Konfiguration aus den folgenden Ressourcen in der angegebenen Reihenfolge geladen:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="a3e7e-120">*appsettings.json-Datei,* falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="a3e7e-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="a3e7e-121">*Appsettings. Datei "ENVIRONMENT_NAME".json,* falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="a3e7e-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="a3e7e-122">Benutzergeheimnisse Datei auf dem Datenträger, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="a3e7e-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="a3e7e-123">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="a3e7e-123">Environment variables</span></span>
1. <span data-ttu-id="a3e7e-124">Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="a3e7e-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="a3e7e-125">appsettings.json-Format und -Zugriff</span><span class="sxs-lookup"><span data-stu-id="a3e7e-125">appsettings.json format and access</span></span>

<span data-ttu-id="a3e7e-126">Die Datei *appsettings.json* kann hierarchisch sein, wobei Werte wie die folgende JSON strukturiert sind:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

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

<span data-ttu-id="a3e7e-127">Wenn das Konfigurationssystem mit dem vorherigen JSON angezeigt wird, werden untergeordnete Werte abgeflacht und verweise auf ihre vollqualifizierten hierarchischen Pfade.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="a3e7e-128">Ein Doppelpunkt (`:`) trennt jede Eigenschaft in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="a3e7e-129">Der Konfigurationsschlüssel `section1:key0` greift beispielsweise `section1` auf den `key0` Wert des Objektliterals zu.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="a3e7e-130">Benutzergeheimnisse</span><span class="sxs-lookup"><span data-stu-id="a3e7e-130">User secrets</span></span>

<span data-ttu-id="a3e7e-131">Benutzergeheimnisse sind:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-131">User secrets are:</span></span>

* <span data-ttu-id="a3e7e-132">Konfigurationswerte, die in einer JSON-Datei auf der Arbeitsstation des Entwicklers außerhalb des App-Entwicklungsordners gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="a3e7e-133">Nur geladen, wenn `Development` in der Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="a3e7e-134">Zugeordnet mit einer bestimmten App.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-134">Associated with a specific app.</span></span>
* <span data-ttu-id="a3e7e-135">Verwaltet mit dem `user-secrets` Befehl von .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="a3e7e-136">Konfigurieren Sie Ihre App für `user-secrets` den Speicher von Geheimnissen, indem Sie den Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="a3e7e-137">Der vorherige Befehl `UserSecretsId` fügt der Projektdatei ein Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="a3e7e-138">Das Element enthält eine GUID, die zum Zuordnen von Geheimnissen zur App verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="a3e7e-139">Sie können dann mit `set` dem Befehl einen geheimen Schlüssel definieren.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="a3e7e-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="a3e7e-141">Mit dem vorherigen `Parent:ApiKey` Befehl wird der Konfigurationsschlüssel auf `12345`der Arbeitsstation eines Entwicklers mit dem Wert verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="a3e7e-142">Weitere Informationen zum Erstellen, Speichern und Verwalten von Benutzergeheimnissen finden Sie unter Der [sicheren Speicherung von App-Geheimnissen in der Entwicklung in ASP.NET Core-Dokument.](/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="a3e7e-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="a3e7e-143">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="a3e7e-143">Environment variables</span></span>

<span data-ttu-id="a3e7e-144">Der nächste Satz von Werten, die in Ihre App-Konfiguration geladen werden, sind die Umgebungsvariablen des Systems.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="a3e7e-145">Alle Umgebungsvariableneinstellungen Ihres Systems sind Ihnen jetzt über die Konfigurations-API zugänglich.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="a3e7e-146">Hierarchische Werte werden abgeflacht und durch Doppelpunktzeichen getrennt, wenn sie in Ihrer App gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="a3e7e-147">Einige Betriebssysteme lassen jedoch keine Variablennamen für die Doppelpunktzeichenumgebung zu.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="a3e7e-148">ASP.NET Core behebt diese Einschränkung, indem Werte`__`mit doppelten Unterstrichen ( ) in einen Doppelpunkt konvertiert werden, wenn auf sie zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="a3e7e-149">Der `Parent:ApiKey` Wert aus dem Abschnitt Benutzergeheimnisse oben kann `Parent__ApiKey`mit der Umgebungsvariablen überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="a3e7e-150">Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="a3e7e-150">Command-line arguments</span></span>

<span data-ttu-id="a3e7e-151">Die Konfiguration kann auch als Befehlszeilenargumente bereitgestellt werden, wenn Ihre App gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="a3e7e-152">Verwenden Sie die Notation`--`Double-Dash (`/`) oder Forward-Slash ( ), um den Namen des festzulegenden Konfigurationswerts und den zu konfigurierenden Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="a3e7e-153">Die Syntax ähnelt den folgenden Befehlen:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="a3e7e-154">Die Rückkehr von web.config</span><span class="sxs-lookup"><span data-stu-id="a3e7e-154">The return of web.config</span></span>

<span data-ttu-id="a3e7e-155">Wenn Sie Ihre App auf Windows unter IIS bereitgestellt haben, konfiguriert die *Datei web.config* weiterhin IIS zum Verwalten Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="a3e7e-156">Standardmäßig fügt IIS einen Verweis auf das ASP.NET Core Module (ANCM) hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="a3e7e-157">ANCM ist ein natives IIS-Modul, das Ihre App anstelle des Kestrel-Webservers hostet.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="a3e7e-158">Dieser *Web.config-Abschnitt* ähnelt dem folgenden XML-Markup:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-158">This *web.config* section resembles the following XML markup:</span></span>

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

<span data-ttu-id="a3e7e-159">Die App-spezifische Konfiguration kann durch `environmentVariables` Verschachteln eines Elements im `aspNetCore` Element definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="a3e7e-160">Die in diesem Abschnitt definierten Werte werden der ASP.NET Core-App als Umgebungsvariablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="a3e7e-161">Die Umgebungsvariablen werden während dieses Segments des App-Startvorgangs entsprechend geladen.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-161">The environment variables load appropriately during that segment of app startup.</span></span>

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

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="a3e7e-162">Lesen der Konfiguration in der App</span><span class="sxs-lookup"><span data-stu-id="a3e7e-162">Read configuration in the app</span></span>

<span data-ttu-id="a3e7e-163">ASP.NET Core bietet App-Konfiguration über die <xref:Microsoft.Extensions.Configuration.IConfiguration> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="a3e7e-164">Diese Konfigurationsschnittstelle sollte von Ihren Blazor-Komponenten, Blazor-Seiten und allen anderen ASP.NET Core-verwalteten Klasse angefordert werden, die Zugriff auf die Konfiguration benötigt.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="a3e7e-165">Das ASP.NET Core-Framework füllt diese Schnittstelle automatisch mit der zuvor konfigurierten aufgelösten Konfiguration auf.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="a3e7e-166">Auf einer Blazor-Seite oder dem Razor-Markup `IConfiguration` einer Komponente `@inject` können Sie das Objekt mit einer Direktive oben in der *.razor-Datei* wie folgt einfügen:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="a3e7e-167">Diese vorhergehende `IConfiguration` Anweisung macht `Configuration` das Objekt als Variable für den Rest der Razor-Vorlage verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="a3e7e-168">Einzelne Konfigurationseinstellungen können gelesen werden, indem die Konfigurationseinstellungshierarchie als Indexerparameter gesucht wird:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="a3e7e-169">Sie können ganze Konfigurationsabschnitte abrufen, indem Sie die <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> Methode verwenden, um eine `GetSection("section1")` Sammlung von Schlüsseln an einem bestimmten Speicherort abzurufen, deren Syntax dem Abrufen der Konfiguration für Abschnitt1 aus dem vorherigen Beispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="a3e7e-170">Stark typisierte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a3e7e-170">Strongly typed configuration</span></span>

<span data-ttu-id="a3e7e-171">Mit Web Forms war es möglich, einen stark typisierten <xref:System.Configuration.ConfigurationSection> Konfigurationstyp zu erstellen, der vom Typ und den zugeordneten Typen geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="a3e7e-172">A `ConfigurationSection` ermöglicht es Ihnen, einige Geschäftsregeln und die Verarbeitung für diese Konfigurationswerte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="a3e7e-173">In ASP.NET Core können Sie eine Klassenhierarchie angeben, die die Konfigurationswerte empfängt.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="a3e7e-174">Diese Klassen:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-174">These classes:</span></span>

* <span data-ttu-id="a3e7e-175">Sie müssen nicht von einer übergeordneten Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="a3e7e-176">Soll `public` Eigenschaften enthalten, die den Eigenschaften und Typreferenzen für die Konfigurationsstruktur entsprechen, die Sie erfassen möchten.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="a3e7e-177">Für das frühere *Beispiel appsettings.json* können Sie die folgenden Klassen definieren, um die Werte zu erfassen:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

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

<span data-ttu-id="a3e7e-178">Diese Klassenhierarchie kann aufgefüllt werden, `Startup.ConfigureServices` indem der Methode die folgende Zeile hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="a3e7e-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="a3e7e-179">Im Rest der App können Sie Klassen einen Eingabeparameter oder eine `@inject` Direktive in Razor-Vorlagen vom Typ `IOptions<MyConfig>` hinzufügen, um die stark typisierten Konfigurationseinstellungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="a3e7e-180">Die `IOptions<MyConfig>.Value` Eigenschaft gibt `MyConfig` den Wert ab, der aus den Konfigurationseinstellungen ausgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="a3e7e-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="a3e7e-181">Weitere Informationen zur Optionen-Funktion finden Sie im [Optionsmuster in ASP.NET Core-Dokument.](/aspnet/core/fundamentals/configuration/options#options-interfaces)</span><span class="sxs-lookup"><span data-stu-id="a3e7e-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a3e7e-182">[VorherigeS](middleware.md)
>[Weiter](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="a3e7e-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
