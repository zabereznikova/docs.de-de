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
# <a name="app-configuration"></a>App-Konfiguration

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Die primäre Möglichkeit zum Laden der App-Konfiguration in Web&mdash;Forms besteht in Einträgen in der *Datei web.config* entweder auf dem Server oder in einer zugehörigen Konfigurationsdatei, auf die von *web.config*verwiesen wird. Sie können das `ConfigurationManager` statische Objekt verwenden, um mit App-Einstellungen, Daten-Repository-Verbindungszeichenfolgen und anderen erweiterten Konfigurationsanbietern zu interagieren, die der App hinzugefügt werden. Es ist typisch, Interaktionen mit der App-Konfiguration zu sehen, wie im folgenden Code zu sehen:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

Mit ASP.NET Core und dem serverseitigen Blazor kann die *web.config-Datei* vorhanden sein, wenn Ihre App auf einem Windows IIS-Server gehostet wird. Es gibt jedoch `ConfigurationManager` keine Interaktion mit dieser Konfiguration, und Sie können eine strukturiertere App-Konfiguration aus anderen Quellen erhalten. Werfen wir einen Blick darauf, wie die Konfiguration erfasst wird und wie Sie weiterhin über eine *web.config-Datei* auf Konfigurationsinformationen zugreifen können.

## <a name="configuration-sources"></a>Konfigurationsquellen

ASP.NET Core erkennt, dass es viele Konfigurationsquellen gibt, die Sie möglicherweise für Ihre App verwenden möchten. Das Framework versucht, Ihnen standardmäßig das Beste aus diesen Funktionen anzubieten. Die Konfiguration wird von ASP.NET Core aus diesen verschiedenen Quellen gelesen und aggregiert. Später geladene Werte für denselben Konfigurationsschlüssel haben Vorrang vor früheren Werten.

ASP.NET Core wurde entwickelt, um Cloud-bewusst zu sein und die Konfiguration von Apps sowohl für Betreiber als auch für Entwickler zu vereinfachen. ASP.NET Core ist umgebungsbewusst und weiß, `Production` ob `Development` es in Ihrer Umgebung ausgeführt wird. Der Umgebungsindikator wird `ASPNETCORE_ENVIRONMENT` in der Systemumgebungsvariablen gesetzt. Wenn kein Wert konfiguriert ist, wird die `Production` App standardmäßig in der Umgebung ausgeführt.

Ihre App kann die Konfiguration aus mehreren Quellen basierend auf dem Namen der Umgebung auslösen und hinzufügen. Standardmäßig wird die Konfiguration aus den folgenden Ressourcen in der angegebenen Reihenfolge geladen:

1. *appsettings.json-Datei,* falls vorhanden
1. *Appsettings. Datei "ENVIRONMENT_NAME".json,* falls vorhanden
1. Benutzergeheimnisse Datei auf dem Datenträger, falls vorhanden
1. Umgebungsvariablen
1. Befehlszeilenargumente

## <a name="appsettingsjson-format-and-access"></a>appsettings.json-Format und -Zugriff

Die Datei *appsettings.json* kann hierarchisch sein, wobei Werte wie die folgende JSON strukturiert sind:

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

Wenn das Konfigurationssystem mit dem vorherigen JSON angezeigt wird, werden untergeordnete Werte abgeflacht und verweise auf ihre vollqualifizierten hierarchischen Pfade. Ein Doppelpunkt (`:`) trennt jede Eigenschaft in der Hierarchie. Der Konfigurationsschlüssel `section1:key0` greift beispielsweise `section1` auf den `key0` Wert des Objektliterals zu.

## <a name="user-secrets"></a>Benutzergeheimnisse

Benutzergeheimnisse sind:

* Konfigurationswerte, die in einer JSON-Datei auf der Arbeitsstation des Entwicklers außerhalb des App-Entwicklungsordners gespeichert sind.
* Nur geladen, wenn `Development` in der Umgebung ausgeführt wird.
* Zugeordnet mit einer bestimmten App.
* Verwaltet mit dem `user-secrets` Befehl von .NET Core CLI.

Konfigurieren Sie Ihre App für `user-secrets` den Speicher von Geheimnissen, indem Sie den Befehl ausführen:

```dotnetcli
dotnet user-secrets init
```

Der vorherige Befehl `UserSecretsId` fügt der Projektdatei ein Element hinzu. Das Element enthält eine GUID, die zum Zuordnen von Geheimnissen zur App verwendet wird. Sie können dann mit `set` dem Befehl einen geheimen Schlüssel definieren. Beispiel:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

Mit dem vorherigen `Parent:ApiKey` Befehl wird der Konfigurationsschlüssel auf `12345`der Arbeitsstation eines Entwicklers mit dem Wert verfügbar.

Weitere Informationen zum Erstellen, Speichern und Verwalten von Benutzergeheimnissen finden Sie unter Der [sicheren Speicherung von App-Geheimnissen in der Entwicklung in ASP.NET Core-Dokument.](/aspnet/core/security/app-secrets)

## <a name="environment-variables"></a>Umgebungsvariablen

Der nächste Satz von Werten, die in Ihre App-Konfiguration geladen werden, sind die Umgebungsvariablen des Systems. Alle Umgebungsvariableneinstellungen Ihres Systems sind Ihnen jetzt über die Konfigurations-API zugänglich. Hierarchische Werte werden abgeflacht und durch Doppelpunktzeichen getrennt, wenn sie in Ihrer App gelesen werden. Einige Betriebssysteme lassen jedoch keine Variablennamen für die Doppelpunktzeichenumgebung zu. ASP.NET Core behebt diese Einschränkung, indem Werte`__`mit doppelten Unterstrichen ( ) in einen Doppelpunkt konvertiert werden, wenn auf sie zugegriffen wird. Der `Parent:ApiKey` Wert aus dem Abschnitt Benutzergeheimnisse oben kann `Parent__ApiKey`mit der Umgebungsvariablen überschrieben werden.

## <a name="command-line-arguments"></a>Befehlszeilenargumente

Die Konfiguration kann auch als Befehlszeilenargumente bereitgestellt werden, wenn Ihre App gestartet wird. Verwenden Sie die Notation`--`Double-Dash (`/`) oder Forward-Slash ( ), um den Namen des festzulegenden Konfigurationswerts und den zu konfigurierenden Wert anzugeben. Die Syntax ähnelt den folgenden Befehlen:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>Die Rückkehr von web.config

Wenn Sie Ihre App auf Windows unter IIS bereitgestellt haben, konfiguriert die *Datei web.config* weiterhin IIS zum Verwalten Ihrer App. Standardmäßig fügt IIS einen Verweis auf das ASP.NET Core Module (ANCM) hinzu. ANCM ist ein natives IIS-Modul, das Ihre App anstelle des Kestrel-Webservers hostet. Dieser *Web.config-Abschnitt* ähnelt dem folgenden XML-Markup:

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

Die App-spezifische Konfiguration kann durch `environmentVariables` Verschachteln eines Elements im `aspNetCore` Element definiert werden. Die in diesem Abschnitt definierten Werte werden der ASP.NET Core-App als Umgebungsvariablen angezeigt. Die Umgebungsvariablen werden während dieses Segments des App-Startvorgangs entsprechend geladen.

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

## <a name="read-configuration-in-the-app"></a>Lesen der Konfiguration in der App

ASP.NET Core bietet App-Konfiguration über die <xref:Microsoft.Extensions.Configuration.IConfiguration> Schnittstelle. Diese Konfigurationsschnittstelle sollte von Ihren Blazor-Komponenten, Blazor-Seiten und allen anderen ASP.NET Core-verwalteten Klasse angefordert werden, die Zugriff auf die Konfiguration benötigt. Das ASP.NET Core-Framework füllt diese Schnittstelle automatisch mit der zuvor konfigurierten aufgelösten Konfiguration auf. Auf einer Blazor-Seite oder dem Razor-Markup `IConfiguration` einer Komponente `@inject` können Sie das Objekt mit einer Direktive oben in der *.razor-Datei* wie folgt einfügen:

```razor
@inject IConfiguration Configuration
```

Diese vorhergehende `IConfiguration` Anweisung macht `Configuration` das Objekt als Variable für den Rest der Razor-Vorlage verfügbar.

Einzelne Konfigurationseinstellungen können gelesen werden, indem die Konfigurationseinstellungshierarchie als Indexerparameter gesucht wird:

```csharp
var mySetting = Configuration["section1:key0"];
```

Sie können ganze Konfigurationsabschnitte abrufen, indem Sie die <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> Methode verwenden, um eine `GetSection("section1")` Sammlung von Schlüsseln an einem bestimmten Speicherort abzurufen, deren Syntax dem Abrufen der Konfiguration für Abschnitt1 aus dem vorherigen Beispiel ähnelt.

## <a name="strongly-typed-configuration"></a>Stark typisierte Konfiguration

Mit Web Forms war es möglich, einen stark typisierten <xref:System.Configuration.ConfigurationSection> Konfigurationstyp zu erstellen, der vom Typ und den zugeordneten Typen geerbt wurde. A `ConfigurationSection` ermöglicht es Ihnen, einige Geschäftsregeln und die Verarbeitung für diese Konfigurationswerte zu konfigurieren.

In ASP.NET Core können Sie eine Klassenhierarchie angeben, die die Konfigurationswerte empfängt. Diese Klassen:

* Sie müssen nicht von einer übergeordneten Klasse erben.
* Soll `public` Eigenschaften enthalten, die den Eigenschaften und Typreferenzen für die Konfigurationsstruktur entsprechen, die Sie erfassen möchten.

Für das frühere *Beispiel appsettings.json* können Sie die folgenden Klassen definieren, um die Werte zu erfassen:

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

Diese Klassenhierarchie kann aufgefüllt werden, `Startup.ConfigureServices` indem der Methode die folgende Zeile hinzugefügt wird:

```csharp
services.Configure<MyConfig>(Configuration);
```

Im Rest der App können Sie Klassen einen Eingabeparameter oder eine `@inject` Direktive in Razor-Vorlagen vom Typ `IOptions<MyConfig>` hinzufügen, um die stark typisierten Konfigurationseinstellungen zu erhalten. Die `IOptions<MyConfig>.Value` Eigenschaft gibt `MyConfig` den Wert ab, der aus den Konfigurationseinstellungen ausgefüllt wird.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Weitere Informationen zur Optionen-Funktion finden Sie im [Optionsmuster in ASP.NET Core-Dokument.](/aspnet/core/fundamentals/configuration/options#options-interfaces)

>[!div class="step-by-step"]
>[VorherigeS](middleware.md)
>[Weiter](security-authentication-authorization.md)
