---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 2c82dda2d93225edb360316637e22964135cd5e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512554"
---
# <a name="dotnet-new"></a>dotnet new

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.

## <a name="synopsis"></a>Übersicht

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a>Beschreibung 

Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.

Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.

## <a name="arguments"></a>Argumente

`TEMPLATE`

Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird. Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können. Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

Der Befehl enthält eine Standardliste mit Vorlagen. Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen. In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind. Die Standardsprache für die Vorlage wird in den Klammern angezeigt.

|Vorlagenbeschreibung                          | Vorlagenname   | Sprachen     |
|----------------------------------------------|-----------------|---------------|
| Konsolenanwendung                          | `console`       | [C#], F#, VB  |
| Klassenbibliothek                                | `classlib`      | [C#], F#, VB  |
| Unittestprojekt                            | `mstest`        | [C#], F#, VB  |
| xUnit-Testprojekt                           | `xunit`         | [C#], F#, VB  |
| Seite „Razor“                                   | `page`          | [C#]          |
| MVC ViewImports                              | `viewimports`   | [C#]          |
| MVC ViewStart                                | `viewstart`     | [C#]          |
| ASP.NET Core leer                           | `web`           | [C#], F#      |
| ASP.NET Core-Web-App (Model-View-Controller) | `mvc`           | [C#], F#      |
| ASP.NET Core-Web-App                         | `razor`         | [C#]          |
| ASP.NET Core mit Angular                    | `angular`       | [C#]          |
| ASP.NET Core mit React.js                   | `react`         | [C#]          |
| ASP.NET Core mit React.js und Redux         | `reactredux`    | [C#]          |
| ASP.NET Core-Web-API                         | `webapi`        | [C#], F#      |
| Razor-Klassenbibliothek                          | `razorclasslib` | [C#]          |
| global.json-Datei                             | `globaljson`    |               |
| NuGet-Konfiguration                                 | `nugetconfig`   |               |
| Web-Konfiguration                                   | `webconfig`     |               |
| Projektmappendatei                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

Der Befehl enthält eine Standardliste mit Vorlagen. Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen. In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind. Die Standardsprache für die Vorlage wird in den Klammern angezeigt.

|Vorlagenbeschreibung                          | Vorlagenname | Sprachen     |
|----------------------------------------------|---------------|---------------|
| Konsolenanwendung                          | `console`     | [C#], F#, VB  |
| Klassenbibliothek                                | `classlib`    | [C#], F#, VB  |
| Unittestprojekt                            | `mstest`      | [C#], F#, VB  |
| xUnit-Testprojekt                           | `xunit`       | [C#], F#, VB  |
| ASP.NET Core leer                           | `web`         | [C#], F#      |
| ASP.NET Core-Web-App (Model-View-Controller) | `mvc`         | [C#], F#      |
| ASP.NET Core-Web-App                         | `razor`       | [C#]          |
| ASP.NET Core mit Angular                    | `angular`     | [C#]          |
| ASP.NET Core mit React.js                   | `react`       | [C#]          |
| ASP.NET Core mit React.js und Redux         | `reactredux`  | [C#]          |
| ASP.NET Core-Web-API                         | `webapi`      | [C#], F#      |
| global.json-Datei                             | `globaljson`  |               |
| NuGet-Konfiguration                                 | `nugetconfig` |               |
| Web-Konfiguration                                   | `webconfig`   |               |
| Projektmappendatei                                | `sln`         |               |
| Seite „Razor“                                   | `page`        |               |
| MVC ViewImports                              | `viewimports` |               |
| MVC ViewStart                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Der Befehl enthält eine Standardliste mit Vorlagen. Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen. In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind. Die Standardsprache für die Vorlage wird in den Klammern angezeigt.

|Vorlagenbeschreibung  | Vorlagenname | Sprachen |
|----------------------|---------------|-----------|
| Konsolenanwendung  | `console`     | [C#], F#  |
| Klassenbibliothek        | `classlib`    | [C#], F#  |
| Unittestprojekt    | `mstest`      | [C#], F#  |
| xUnit-Testprojekt   | `xunit`       | [C#], F#  |
| ASP.NET Core leer   | `web`         | [C#]      |
| ASP.NET Core-Web-App | `mvc`         | [C#], F#  |
| ASP.NET Core-Web-API | `webapi`      | [C#]      |
| NuGet-Konfiguration         | `nugetconfig` |           |
| Web-Konfiguration           | `webconfig`   |           |
| Projektmappendatei        | `sln`         |           |

---

## <a name="options"></a>Optionen

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--force`

Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden. Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.

`-h|--help`

Druckt Hilfe für den Befehl. Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.

`-i|--install <PATH|NUGET_ID>`

Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`. Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben. Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt. Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).

Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).

`-l|--list`

Listet Vorlagen auf, die den angegebenen Namen enthalten. Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind. Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.

`-lang|--language {C#|F#|VB}`

Gibt die Sprache der zu erstellenden Vorlage an. Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)). Für einige Vorlagen nicht gültig.

> [!NOTE]
> Einige Shells interpretieren `#` als Sonderzeichen. In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Der Name für die erstellte Ausgabe. Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.

`--nuget-source`

Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.

`-o|--output <OUTPUT_DIRECTORY>`

Speicherort für die generierte Ausgabe. Der Standardwert ist das aktuelle Verzeichnis.

`--type`

Filtert Vorlagen auf Grundlage verfügbarer Typen. Vordefinierte Werte sind „project“, „item“ oder „other“.

`-u|--uninstall <PATH|NUGET_ID>`

Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.

> [!NOTE]
> Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren. Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.
> Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--force`

Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden. Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.

`-h|--help`

Druckt Hilfe für den Befehl. Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.

`-i|--install <PATH|NUGET_ID>`

Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`. Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben. Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt. Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).

Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).

`-l|--list`

Listet Vorlagen auf, die den angegebenen Namen enthalten. Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind. Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.

`-lang|--language {C#|F#|VB}`

Gibt die Sprache der zu erstellenden Vorlage an. Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)). Für einige Vorlagen nicht gültig.

> [!NOTE]
> Einige Shells interpretieren `#` als Sonderzeichen. In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Der Name für die erstellte Ausgabe. Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.

`-o|--output <OUTPUT_DIRECTORY>`

Speicherort für die generierte Ausgabe. Der Standardwert ist das aktuelle Verzeichnis.

`--type`

Filtert Vorlagen auf Grundlage verfügbarer Typen. Vordefinierte Werte sind „project“, „item“ oder „other“.

`-u|--uninstall <PATH|NUGET_ID>`

Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.

> [!NOTE]
> Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren. Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.
> Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-all|--show-all`

Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an. Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert. Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.

`-h|--help`

Druckt Hilfe für den Befehl. Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.

`-l|--list`

Listet Vorlagen auf, die den angegebenen Namen enthalten. Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind. Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.

`-lang|--language {C#|F#}`

Gibt die Sprache der zu erstellenden Vorlage an. Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)). Für einige Vorlagen nicht gültig.

> [!NOTE]
> Einige Shells interpretieren `#` als Sonderzeichen. In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

Der Name für die erstellte Ausgabe. Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.

`-o|--output <OUTPUT_DIRECTORY>`

Speicherort für die generierte Ausgabe. Der Standardwert ist das aktuelle Verzeichnis.

---

## <a name="template-options"></a>Vorlagenoptionen

Für jede Projektvorlage kann es zusätzliche Optionen geben. Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

**console, angular, react, reactredux, razorclasslib**

  `--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**classlib**

`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen. Der Standardwert ist `netstandard2.0`.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**mstest, xunit**

`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.

**web**

`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

`--no-https`: Für das Projekt ist HTTPS nicht erforderlich. Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

- `None`: keine Authentifizierung (Standard)
- `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
- `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten
- `Windows`: Windows-Authentifizierung

`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

`--client-id <ID>`: Die Client-ID für dieses Projekt. Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.

`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.

`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

`--no-https`: Für das Projekt ist HTTPS nicht erforderlich. `app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt. Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

- `None`: keine Authentifizierung (Standard)
- `Individual`: einzelne Authentifizierung
- `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
- `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten
- `MultiOrg`: Organisationauthentifizierung für mehrere Mandanten
- `Windows`: Windows-Authentifizierung

`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt Mit der `IndividualB2C`-Authentifizierung verwenden.

`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt Mit der `IndividualB2C`-Authentifizierung verwenden

`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

`--client-id <ID>`: Die Client-ID für dieses Projekt. Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `/signin-oidc`.

`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.

`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.

`--use-browserlink`: enthält BrowserLink im Projekt

`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

`--no-https`: Für das Projekt ist HTTPS nicht erforderlich. `app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt. Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.

**page**

`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an. Der Standardwert ist `MyApp.Namespace`.

`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an. Der Standardwert ist `MyApp.Namespace`.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

**console, angular, react, reactredux**

  `--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**classlib**

`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen. Der Standardwert ist `netstandard2.0`.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**mstest, xunit**

`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.

**web**

`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

- `None`: keine Authentifizierung (Standard)
- `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
- `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten
- `Windows`: Windows-Authentifizierung

`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

`--client-id <ID>`: Die Client-ID für dieses Projekt. Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung

`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.

`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

- `None`: keine Authentifizierung (Standard)
- `Individual`: einzelne Authentifizierung
- `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
- `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten
- `MultiOrg`: Organisationauthentifizierung für mehrere Mandanten
- `Windows`: Windows-Authentifizierung

`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt Mit der `IndividualB2C`-Authentifizierung verwenden.

`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt Mit der `IndividualB2C`-Authentifizierung verwenden

`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

`--client-id <ID>`: Die Client-ID für dieses Projekt. Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `/signin-oidc`.

`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung

`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.

`--use-browserlink`: enthält BrowserLink im Projekt

`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.

`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.

**page**

`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an. Der Standardwert ist `MyApp.Namespace`.

`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an. Der Standardwert ist `MyApp.Namespace`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**console, xunit, mstest, web, webapi**

`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp1.0` oder `netcoreapp1.1` Der Standardwert ist `netcoreapp1.0`.

**classlib**

`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6` Der Standardwert ist `netstandard1.4`.

**mvc**

`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll. Werte: `netcoreapp1.0` oder `netcoreapp1.1` Der Standardwert ist `netcoreapp1.0`.

`-au|--auth`: Der zu verwendende Authentifizierungstyp. Werte: `None` oder `Individual` Der Standardwert ist `None`.

`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll. Werte: `true` oder `false` Der Standardwert ist `false`.

---

## <a name="examples"></a>Beispiele

Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:

`dotnet new console -lang F#`

Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):

`dotnet new classlib -lang VB -o MyLibrary`

Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung:

`dotnet new mvc -au None`

Erstellen Sie eine neue xUnit-Anwendung:

`dotnet new xunit`

Liste Sie alle für MVC verfügbaren Vorlagen auf:

`dotnet new mvc -l`

Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a>Siehe auch

* [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md)  
* [Erstellen eines benutzerdefinierten Vorlagen-Assistenten](~/docs/core/tutorials/create-custom-template.md)  
* [dotnet/dotnet-template-samples-GitHub-Repository](https://github.com/dotnet/dotnet-template-samples)  
* [Verfügbare Vorlagen für dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
