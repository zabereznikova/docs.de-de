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
# <a name="app-configuration"></a>App-Konfiguration

Die primäre Methode zum Laden der APP-Konfiguration in Web Forms ist die Verwendung von Einträgen in der *web.config* Datei &mdash; auf dem Server oder einer zugehörigen Konfigurationsdatei, auf die von *web.config*verwiesen wird. Sie können das statische `ConfigurationManager` Objekt für die Interaktion mit App-Einstellungen, Datenrepository-Verbindungs Zeichenfolgen und anderen erweiterten Konfigurations Anbietern verwenden, die der app hinzugefügt werden. Es ist üblich, Interaktionen mit der APP-Konfiguration wie im folgenden Code zu sehen:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

BlazorWenn *web.config* die APP auf einem Windows IIS-Server gehostet wird, kann ASP.net Core und serverseitig vorhanden sein. Es gibt jedoch keine `ConfigurationManager` Interaktion mit dieser Konfiguration, und Sie können eine strukturiertere App-Konfiguration aus anderen Quellen erhalten. Sehen wir uns nun an, wie die Konfiguration erfasst wird und wie Sie weiterhin über eine *web.config* Datei auf Konfigurationsinformationen zugreifen können.

## <a name="configuration-sources"></a>Konfigurationsquellen

ASP.net Core erkennt, dass es viele Konfigurations Quellen gibt, die Sie möglicherweise für Ihre APP verwenden möchten. Das Framework versucht, Ihnen standardmäßig das beste dieser Features anzubieten. Die Konfiguration wird aus diesen verschiedenen Quellen durch ASP.net Core gelesen und aggregiert. Später geladene Werte für denselben Konfigurationsschlüssel haben Vorrang vor früheren Werten.

ASP.net Core wurde in der Cloud unterstützt und erleichtert die Konfiguration von Apps für Operatoren und Entwickler. ASP.net Core ist für die Umgebung von der Umgebung abhängig und weiß, ob Sie in ihrer-oder-Umgebung ausgeführt wird `Production` `Development` . Der Umgebungs Indikator wird in der `ASPNETCORE_ENVIRONMENT` System Umgebungsvariablen festgelegt. Wenn kein Wert konfiguriert ist, wird die App standardmäßig in der `Production` Umgebung ausgeführt.

Ihre APP kann basierend auf dem Namen der Umgebung eine Konfiguration aus mehreren Quellen initiieren und hinzufügen. Standardmäßig wird die Konfiguration aus den folgenden Ressourcen in der aufgeführten Reihenfolge geladen:

1. Datei *appsettings.js* (sofern vorhanden)
1. *appSettings. {ENVIRONMENT_NAME}. JSON* -Datei, falls vorhanden
1. Benutzer Geheimnis Datei auf Datenträger, falls vorhanden
1. Umgebungsvariablen
1. Befehlszeilenargumente

## <a name="appsettingsjson-format-and-access"></a>appsettings.jsvon Format und Zugriff

Die *appsettings.jsfür* die Datei kann hierarchisch sein, wobei die Werte wie im folgenden JSON-Code strukturiert sind:

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

Wenn das Konfigurationssystem mit dem vorangehenden JSON-Code dargestellt wird, werden untergeordnete Werte vereinfacht und auf die voll qualifizierten hierarchischen Pfade verwiesen. Ein Doppelpunkt ( `:` ) trennt jede Eigenschaft in der Hierarchie. Beispielsweise greift der Konfigurationsschlüssel auf `section1:key0` den `section1` Wert des Objektliterals zu `key0` .

## <a name="user-secrets"></a>Benutzer Geheimnisse

Benutzer Geheimnisse:

* Konfigurationswerte, die in einer JSON-Datei auf der Arbeitsstation des Entwicklers außerhalb des App-Entwicklungs Ordners gespeichert sind.
* Wird nur geladen, wenn in der Umgebung ausgeführt wird `Development` .
* Einer bestimmten app zugeordnet.
* Wird mit dem-Befehl des .net Core-CLI verwaltet `user-secrets` .

Konfigurieren Sie Ihre APP für die Speicherung von geheimen Schlüsseln durch Ausführen des folgenden `user-secrets` Befehls:

```dotnetcli
dotnet user-secrets init
```

Mit dem vorangehenden Befehl wird `UserSecretsId` der Projektdatei ein-Element hinzugefügt. Das-Element enthält eine GUID, die verwendet wird, um Geheimnisse der APP zuzuordnen. Anschließend können Sie mit dem Befehl ein Geheimnis definieren `set` . Beispiel:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

Der vorherige Befehl macht den `Parent:ApiKey` Konfigurationsschlüssel auf der Arbeitsstation eines Entwicklers mit dem Wert verfügbar `12345` .

Weitere Informationen zum Erstellen, speichern und Verwalten von Benutzer Geheimnissen finden Sie unter [sichere Speicherung von App-Geheimnissen in der Entwicklung in ASP.net Core](/aspnet/core/security/app-secrets) Dokument.

## <a name="environment-variables"></a>Umgebungsvariablen

Die nächste Gruppe von Werten, die in Ihre APP-Konfiguration geladen werden, sind die Umgebungsvariablen des Systems. Alle Umgebungsvariablen Einstellungen Ihres Systems sind nun über die Konfigurations-API zugänglich. Hierarchische Werte werden vereinfacht und durch Doppelpunkte getrennt, wenn Sie in der APP gelesen werden. Allerdings lassen einige Betriebssysteme die Umgebungsvariablen Namen des Doppelpunkts nicht zu. ASP.net Core adressiert diese Einschränkung, indem Werte, die doppelte Unterstriche () aufweisen, `__` beim Zugriff in einen Doppelpunkt umgewandelt werden. Der `Parent:ApiKey` Wert aus dem obigen Abschnitt "Benutzer Geheimnisse" kann mit der Umgebungsvariablen überschrieben werden `Parent__ApiKey` .

## <a name="command-line-arguments"></a>Befehlszeilenargumente

Die Konfiguration kann auch als Befehlszeilenargumente bereitgestellt werden, wenn Ihre APP gestartet wird. Verwenden Sie die Notation Double-Dash ( `--` ) oder Schrägstrich ( `/` ), um den Namen des festzulegenden Konfigurations Werts und den Wert anzugeben, der konfiguriert werden soll. Die Syntax ähnelt den folgenden Befehlen:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>Die Rückgabe von web.config

Wenn Sie Ihre APP für Windows auf IIS bereitgestellt haben, konfiguriert die *web.config* Datei weiterhin IIS, um Ihre APP zu verwalten. Standardmäßig fügt IIS einen Verweis auf das ASP.net Core Modul (ancm) hinzu. Bei ancm handelt es sich um ein natives IIS-Modul, das Ihre APP anstelle des Kestrel-Webservers hostet. Dieser *web.config* Abschnitt ähnelt dem folgenden XML-Markup:

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

Die APP-spezifische Konfiguration kann definiert werden, indem ein Element im-Element geschachtelt wird `environmentVariables` `aspNetCore` . Die in diesem Abschnitt definierten Werte werden in der ASP.net Core-App als Umgebungsvariablen angezeigt. Die Umgebungsvariablen werden während dieses Segments des App-Starts entsprechend geladen.

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

## <a name="read-configuration-in-the-app"></a>Lesen der Konfiguration in der APP

ASP.net Core bietet die APP-Konfiguration über die- <xref:Microsoft.Extensions.Configuration.IConfiguration> Schnittstelle. Diese Konfigurationsschnittstelle sollte von Ihren Blazor Komponenten, Blazor Seiten und jeder anderen ASP.net Core verwalteten Klasse angefordert werden, die Zugriff auf die Konfiguration benötigt. Das ASP.net Core Framework füllt diese Schnittstelle automatisch mit der zuvor konfigurierten aufgelösten Konfiguration auf. Auf einer Blazor Seite oder dem Razor-Markup einer Komponente können Sie das `IConfiguration` Objekt wie folgt mit einer- `@inject` Direktive am Anfang der *Razor* -Datei einfügen:

```razor
@inject IConfiguration Configuration
```

Diese vorangehende Anweisung macht das `IConfiguration` Objekt in der `Configuration` gesamten Razor-Vorlage als Variable verfügbar.

Sie können einzelne Konfigurationseinstellungen lesen, indem Sie die Konfigurations Einstellungs Hierarchie, die als Indexer-Parameter gesucht wurde, angeben:

```csharp
var mySetting = Configuration["section1:key0"];
```

Sie können ganze Konfigurations Abschnitte abrufen, indem Sie die- <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> Methode verwenden, um eine Auflistung von Schlüsseln an einem bestimmten Speicherort mit einer ähnlichen Syntax wie zum `GetSection("section1")` Abrufen der Konfiguration für Section1 aus dem vorherigen Beispiel abzurufen.

## <a name="strongly-typed-configuration"></a>Stark typisierte Konfiguration

Mit Web Forms war es möglich, einen stark typisierten Konfigurationstyp zu erstellen, der vom <xref:System.Configuration.ConfigurationSection> Typ und den zugeordneten Typen geerbt wurde. `ConfigurationSection`Mit können Sie einige Geschäftsregeln und die Verarbeitung für diese Konfigurationswerte konfigurieren.

In ASP.net Core können Sie eine Klassenhierarchie angeben, die die Konfigurationswerte empfängt. Diese Klassen:

* Muss nicht von einer übergeordneten Klasse erben.
* Sollte `public` Eigenschaften enthalten, die mit den Eigenschaften und Typverweisen für die Konfigurations Struktur, die Sie erfassen möchten, identisch sind.

Für den früheren *appsettings.jszum* Beispiel könnten Sie die folgenden Klassen definieren, um die Werte zu erfassen:

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

Diese Klassenhierarchie kann ausgefüllt werden, indem der-Methode die folgende Zeile hinzugefügt wird `Startup.ConfigureServices` :

```csharp
services.Configure<MyConfig>(Configuration);
```

Im Rest der App können Sie Klassen oder eine- `@inject` Direktive in Razor-Vorlagen des Typs einen Eingabeparameter hinzufügen, `IOptions<MyConfig>` um die stark typisierten Konfigurationseinstellungen zu erhalten. Die- `IOptions<MyConfig>.Value` Eigenschaft ergibt den `MyConfig` Wert, der von den Konfigurationseinstellungen aufgefüllt wird.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Weitere Informationen zu den Optionen finden Sie im [options Muster in ASP.net Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) Dokument.

>[!div class="step-by-step"]
>[Zurück](middleware.md)
>[Weiter](security-authentication-authorization.md)
