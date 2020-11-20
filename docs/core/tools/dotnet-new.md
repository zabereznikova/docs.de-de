---
title: Befehl „dotnet new“
description: Der Befehl „dotnet new“ erstellt neue .NET-Projekte auf Basis der angegebenen Vorlage.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/04/2020
ms.openlocfilehash: 3ee644f05ea5929ffc7b11054ef1d974b811f418
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634454"
---
# <a name="dotnet-new"></a>dotnet new

**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet new` erstellt ein .NET-Projekt oder andere Artefakte auf Grundlage einer Vorlage.

Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.

### <a name="implicit-restore"></a>Implizite Wiederherstellung

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argumente

- **`TEMPLATE`**

  Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird. Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können. Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).

  Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen. Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.

  Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:

  - Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.
  - Wenn eine neuere Version der Vorlage verfügbar ist. In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.

  Die folgende Tabelle zeigt die Vorlagen, die im Lieferumfang des .NET SDK enthalten sind. Die Standardsprache für die Vorlage wird in den Klammern angezeigt. Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.

| Vorlagen                                    | Kurzname                      | Sprache     | Tags                                  | Eingeführt |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| Konsolenanwendung                          | [console](#console)             | [C#], F#, VB | Common/Console                        | 1.0        |
| Klassenbibliothek                                | [classlib](#classlib)           | [C#], F#, VB | Common/Library                        | 1.0        |
| WPF-Anwendung                              | [wpf](#wpf)                     | [C#], VB     | Common/WPF                            | 3.0 (5.0 für VB)|
| WPF-Klassenbibliothek                            | [wpflib](#wpf)                  | [C#], VB     | Common/WPF                            | 3.0 (5.0 für VB)|
| WPF-Benutzerdefinierte Steuerelementbibliothek                   | [wpfcustomcontrollib](#wpf)     | [C#], VB     | Common/WPF                            | 3.0 (5.0 für VB)|
| Bibliothek mit WPF-Benutzersteuerelementen                     | [wpfcustomcontrollib](#wpf)       | [C#], VB     | Common/WPF                            | 3.0 (5.0 für VB)|
| Windows Forms-Anwendung (WinForms)         | [winforms](#winforms)           | [C#], VB     | Common/WinForms                       | 3.0 (5.0 für VB)|
| Windows Forms-Klassenbibliothek (WinForms)       | [winforms](#winforms)        | [C#], VB     | Common/WinForms                       | 3.0 (5.0 für VB)|
| Workerdienst                               | [worker](#web-others)           | [C#]         | Common/Worker/Web                     | 3.0        |
| Komponententestprojekt                            | [mstest](#test)                 | [C#], F#, VB | Test/MSTest                           | 1.0        |
| NUnit 3-Testprojekt                         | [nunit](#nunit)                 | [C#], F#, VB | Test/NUnit                            | 2.1.400    |
| NUnit 3-Testelement                            | `nunit-test`                    | [C#], F#, VB | Test/NUnit                            | 2.2        |
| xUnit-Testprojekt                           | [xunit](#test)                  | [C#], F#, VB | Test/xUnit                            | 1.0        |
| Razor-Komponente                              | `razorcomponent`                | [C#]         | Web/ASP.NET                           | 3.0        |
| Seite „Razor“                                   | [page](#page)                   | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewImports                              | [viewimports](#namespace)       | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewStart                                | `viewstart`                     | [C#]         | Web/ASP.NET                           | 2.0        |
| Blazor Server-App                            | [blazorserver](#blazorserver)   | [C#]         | Web/Blazor                            | 3.0        |
| Blazor WebAssembly-App                       | [blazorwasm](#blazorwasm)       | [C#]         | Web/Blazor/WebAssembly                | 3.1.300    |
| ASP.NET Core leer                           | [web](#web)                     | [C#], F#     | Web/Empty                             | 1.0        |
| ASP.NET Core-Web-App (Model-View-Controller) | [mvc](#web-options)             | [C#], F#     | Web/MVC                               | 1.0        |
| ASP.NET Core-Web-App                         | [webapp, razor](#web-options)   | [C#]         | Web/MVC/Razor Pages                   | 2.2, 2.0   |
| ASP.NET Core mit Angular                    | [angular](#spa)                 | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core mit React.js                   | [react](#spa)                   | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core mit React.js und Redux         | [reactredux](#reactredux)       | [C#]         | Web/MVC/SPA                           | 2.0        |
| Razor-Klassenbibliothek                          | [razorclasslib](#razorclasslib) | [C#]         | Web/Razor/Library/Razor Class Library | 2.1        |
| ASP.NET Core-Web-API                         | [webapi](#webapi)               | [C#], F#     | Web/WebAPI                            | 1.0        |
| ASP.NET Core: gRPC-Dienst                    | [grpc](#web-others)             | [C#]         | Web/gRPC                              | 3.0        |
| dotnet: GITIGNORE-Datei                        | `gitignore`                     |              | Konfigurationen                                | 3.0        |
| global.json-Datei                             | [globaljson](#globaljson)       |              | Konfigurationen                                | 2.0        |
| NuGet-Konfiguration                                 | `nugetconfig`                   |              | Konfigurationen                                | 1.0        |
| Dotnet: Manifestdatei des lokalen Tools              | `tool-manifest`                 |              | Konfigurationen                                | 3.0        |
| Web Config                                   | `webconfig`                     |              | Konfigurationen                                | 1.0        |
| Projektmappendatei                                | `sln`                           |              | Lösung                              | 1.0        |
| Protokollpufferdatei                         | [proto](#namespace)             |              | Web/gRPC                              | 3.0        |

## <a name="options"></a>Optionen

- **`--dry-run`**

  Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt. Verfügbar ab .NET Core 2.2 SDK.

- **`--force`**

  Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden. Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.

- **`-h|--help`**

  Druckt Hilfe für den Befehl. Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden. Beispielsweise `dotnet new mvc --help`.

- **`-i|--install <PATH|NUGET_ID>`**

  Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`. Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben. Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt. Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).
  
  Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.

  Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).

- **`-l|--list`**

  Listet Vorlagen auf, die den angegebenen Namen enthalten. Listet alle Vorlagen auf, wenn kein Name angegeben ist.

- **`-lang|--language {C#|F#|VB}`**

  Gibt die Sprache der zu erstellenden Vorlage an. Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)). Für einige Vorlagen nicht gültig.

  > [!NOTE]
  > Einige Shells interpretieren `#` als Sonderzeichen. In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen. Beispielsweise `dotnet new console -lang "F#"`.

- **`-n|--name <OUTPUT_NAME>`**

  Der Name für die erstellte Ausgabe. Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.

- **`--nuget-source <SOURCE>`**

  Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Speicherort für die generierte Ausgabe. Der Standardwert ist das aktuelle Verzeichnis.

- **`--type <TYPE>`**

  Filtert Vorlagen auf Grundlage verfügbarer Typen. Bei `project` und `item` handelt es sich um vordefinierte Werte.

- **`-u|--uninstall [PATH|NUGET_ID]`**

  Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`. Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt. Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.

  Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.

  > [!NOTE]
  > Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren. Beispielsweise funktioniert zwar *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.
  > Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.

- **`--update-apply`**

  Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese. Verfügbar seit .NET Core 3.0 SDK.

- **`--update-check`**

  Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind. Verfügbar seit .NET Core 3.0 SDK.

## <a name="template-options"></a>Vorlagenoptionen

Für jede Projektvorlage kann es zusätzliche Optionen geben. Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:

### <a name="console"></a>Konsole

- **`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Verfügbar seit .NET Core 3.0 SDK.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest. Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3. Wird für F# nicht unterstützt. Verfügbar ab .NET Core 2.2 SDK.

  Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung. Verfügbar ab .NET Core 2.2 SDK.

**_

### <a name="classlib"></a>classlib

- _ *`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Werte: `net5.0` oder `netcoreapp<version>`, um eine .NET-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen. Der Standardwert für das .NET 5.0 SDK ist `net5.0`.

- **`--langVersion <VERSION_NUMBER>`**

  Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest. Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3. Wird für F# nicht unterstützt. Verfügbar ab .NET Core 2.2 SDK.

  Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib

- _ *`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Der Standardwert ist `net5.0`. Verfügbar seit .NET Core 3.1 SDK.

- **`--langVersion <VERSION_NUMBER>`**

  Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest. Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.

  Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="winforms-winformslib"></a><a name="winforms"></a> winforms, winformslib

- _ *`--langVersion <VERSION_NUMBER>`**

  Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest. Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.

  Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="worker-grpc"></a><a name="web-others"></a> worker, grpc

- _ *`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Der Standardwert ist `netcoreapp3.1`. Verfügbar seit .NET Core 3.1 SDK.

- **`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="mstest-xunit"></a><a name="test"></a> mstest, xunit

- _ *`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Die Option ist ab .NET Core 3.0 SDK verfügbar.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="nunit"></a>nunit

- _ *`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.2         | `netcoreapp2.2` |
  | 2.1         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="page"></a>Seite (page)

- _ *`-na|--namespace <NAMESPACE_NAME>`**

  Namespace für den generierten Code. Der Standardwert ist `MyApp.Namespace`.

- **`-np|--no-pagemodel`**

  Erstellt die Seite ohne PageModel.

**_

### <a name="viewimports-proto"></a><a name="namespace"></a> viewimports, proto

- _ *`-na|--namespace <NAMESPACE_NAME>`**

  Namespace für den generierten Code. Der Standardwert ist `MyApp.Namespace`.

**_

### <a name="blazorserver"></a>blazorserver

- _ *`-au|--auth <AUTHENTICATION_TYPE>`**

  Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

  - `None`: keine Authentifizierung (Standard)
  - `Individual`: einzelne Authentifizierung
  - `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
  - `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten
  - `MultiOrg`: Organisationauthentifizierung für mehrere Mandanten
  - `Windows`: Windows-Authentifizierung

- **`--aad-b2c-instance <INSTANCE>`**

  Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`-rp|--reset-password-policy-id <ID>`**

  Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`-ep|--edit-profile-policy-id <ID>`**

  Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`--aad-instance <INSTANCE>`**

  Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  Die Client-ID für dieses Projekt. Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Die Domäne für den Verzeichnismandanten. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

- **`--tenant-id <ID>`**

  Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `/signin-oidc`.

- **`-r|--org-read-access`**

  Erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.

- **`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`--no-https`**

  Deaktiviert HTTPS. Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.

- **`-uld|--use-local-db`**

  Gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="blazorwasm"></a>blazorwasm

- _ *`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

- **`-ho|--hosted`**

  Enthält einen ASP.NET Core-Host für die WebAssembly-App Blazor.

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

  - `None`: keine Authentifizierung (Standard)
  - `Individual`: einzelne Authentifizierung
  - `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
  - `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten

- **`--authority <AUTHORITY>`**

  Die Autorität des OIDC-Anbieters. Mit der `Individual`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

- **`--aad-b2c-instance <INSTANCE>`**

  Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://aadB2CInstance.b2clogin.com/`.

- **`-ssp|--susi-policy-id <ID>`**

  Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`--aad-instance <INSTANCE>`**

  Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  Die Client-ID für dieses Projekt. Wird in eigenständigen Szenarien mit der Authentifizierung `IndividualB2C`, `SingleOrg` oder `Individual` verwendet. Der Standardwert ist `33333333-3333-3333-33333333333333333`.

- **`--domain <DOMAIN>`**

  Die Domäne für den Verzeichnismandanten. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

- **`--app-id-uri <URI>`**

  Der APP-ID-URI für die Server-API, die aufgerufen werden soll. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `api.id.uri`.

- **`--api-client-id <ID>`**

  Die Client-ID für die API, die vom Server gehostet wird. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

- **`-s|--default-scope <SCOPE>`**

  Der API-Bereich, der vom Client angefordert werden muss, um ein Zugriffstoken bereitzustellen. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `user_impersonation`.

- **`--tenant-id <ID>`**

  Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

- **`-r|--org-read-access`**

  Erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`-Authentifizierung.

- **`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`-p|--pwa`**

  Erzeugt eine progressive Webanwendung (PWA), die Installation und Offlinenutzung unterstützt.

- **`--no-https`**

  Deaktiviert HTTPS. Diese Option gilt nur, wenn `Individual`, `IndividualB2C` oder `SingleOrg` für `--auth` nicht verwendet werden.

- **`-uld|--use-local-db`**

  Gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.

- **`--called-api-url <URL>`**

  URL der API, die von der Web-App aufgerufen werden soll. Gilt nur für die Authentifizierung `SingleOrg` oder `IndividualB2C` ohne Angabe eines ASP.NET Core-Hosts. Standardwert: `https://graph.microsoft.com/v1.0/me`.

- **`--calls-graph`**

  Gibt an, ob die Web-App Microsoft Graph aufruft. Gilt nur für die `SingleOrg`-Authentifizierung.

- **`--called-api-scopes <SCOPES>`**

  Bereiche, die angefordert werden müssen, um die API aus der Web-App aufzurufen. Gilt nur für die Authentifizierung `SingleOrg` oder `IndividualB2C` ohne Angabe eines ASP.NET Core-Hosts. Der Standardwert ist `user.read`.

**_

### <a name="web"></a>Web-

- _ *`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Die Option ist nicht in .NET Core 2.2 SDK verfügbar.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.1` |

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

- **`--no-https`**

  Deaktiviert HTTPS.

**_

### <a name="mvc-webapp"></a><a name="web-options"></a> mvc, webapp

- _ *`-au|--auth <AUTHENTICATION_TYPE>`**

  Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

  - `None`: keine Authentifizierung (Standard)
  - `Individual`: einzelne Authentifizierung
  - `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
  - `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten
  - `MultiOrg`: Organisationauthentifizierung für mehrere Mandanten
  - `Windows`: Windows-Authentifizierung

- **`--aad-b2c-instance <INSTANCE>`**

  Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`-rp|--reset-password-policy-id <ID>`**

  Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`-ep|--edit-profile-policy-id <ID>`**

  Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`--aad-instance <INSTANCE>`**

  Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  Die Client-ID für dieses Projekt. Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Die Domäne für den Verzeichnismandanten. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

- **`--tenant-id <ID>`**

  Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung. Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `/signin-oidc`.

- **`-r|--org-read-access`**

  Erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.

- **`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`--no-https`**

  Deaktiviert HTTPS. Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.

- **`-uld|--use-local-db`**

  Gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.

- **`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Die Option ist ab .NET Core 3.0 SDK verfügbar.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

- **`--use-browserlink`**

  Schließt BrowserLink in das Projekt ein. Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.

- **`-rrc|--razor-runtime-compilation`**

  Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist. Die Option ist ab .NET Core SDK 3.1.201 verfügbar.

**_

### <a name="angular-react"></a><a name="spa"></a> angular, react

- _ *`-au|--auth <AUTHENTICATION_TYPE>`**

  Der zu verwendende Authentifizierungstyp. Verfügbar seit .NET Core 3.0 SDK.
  
  Mögliche Werte sind:

  - `None`: keine Authentifizierung (Standard)
  - `Individual`: einzelne Authentifizierung

- **`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

- **`--no-https`**

  Deaktiviert HTTPS. Diese Option gilt nur, wenn die Authentifizierung `None` ist.

- **`-uld|--use-local-db`**

  Gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung. Verfügbar seit .NET Core 3.0 SDK.

- **`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Die Option ist nicht in .NET Core 2.2 SDK verfügbar.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.0` |

**_

### <a name="reactredux"></a>reactredux

- _ *`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Die Option ist nicht in .NET Core 2.2 SDK verfügbar.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.0` |

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

- **`--no-https`**

  Deaktiviert HTTPS.

**_

### <a name="razorclasslib"></a>razorclasslib

- _ *`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

- **`-s|--support-pages-and-views`**

  Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek. Verfügbar seit .NET Core 3.0 SDK.

**_
  
### <a name="webapi"></a>Web-API

- _ *`-au|--auth <AUTHENTICATION_TYPE>`**

  Der zu verwendende Authentifizierungstyp. Mögliche Werte sind:

  - `None`: keine Authentifizierung (Standard)
  - `IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C
  - `SingleOrg`: Organisationauthentifizierung für einzelne Mandanten
  - `Windows`: Windows-Authentifizierung

- **`--aad-b2c-instance <INSTANCE>`**

  Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `IndividualB2C`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt. Mit der `IndividualB2C`-Authentifizierung verwenden

- **`--aad-instance <INSTANCE>`**

  Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  Die Client-ID für dieses Projekt. Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Die Domäne für den Verzeichnismandanten. Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `qualified.domain.name`.

- **`--tenant-id <ID>`**

  Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll. Mit der `SingleOrg`-Authentifizierung verwenden Der Standardwert ist `22222222-2222-2222-2222-222222222222`.

- **`-r|--org-read-access`**

  Erteilt der Anwendung Lesezugriff auf das Verzeichnis. Gilt nur für die `SingleOrg`-Authentifizierung.

- **`--exclude-launch-settings`**

  Schließt *launchSettings.json* aus der generierten Vorlage aus.

- **`--no-https`**

  Deaktiviert HTTPS. `app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt. Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.

- **`-uld|--use-local-db`**

  Gibt an, dass LocalDB statt SQLite verwendet werden soll. Gilt nur für die `IndividualB2C`-Authentifizierung.

- **`-f|--framework <FRAMEWORK>`**

  Gibt das [Zielframework](../../standard/frameworks.md) an. Die Option ist nicht in .NET Core 2.2 SDK verfügbar.

  In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:

  | SDK-Version | Standardwert   |
  |-------------|-----------------|
  | 5.0         | `net5.0`        |
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.1` |

- **`--no-restore`**

  Führt während der Projekterstellung keine implizite Wiederherstellung durch.

**_

### <a name="globaljson"></a>globaljson

- _ *`--sdk-version <VERSION_NUMBER>`**

  Gibt die Version des .NET SDK an, die in der Datei *global.json* verwendet werden soll

***

## <a name="examples"></a>Beispiele

- Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:

  ```dotnetcli
  dotnet new "Console Application"
  ```

- Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:

  ```dotnetcli
  dotnet new mvc -au None
  ```

- Erstellen Sie ein neues xUnit-Projekt:

  ```dotnetcli
  dotnet new xunit
  ```

- Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:

  ```dotnetcli
  dotnet new spa -l
  ```

- Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt. Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.

  ```dotnetcli
  dotnet new we -l
  ```

- Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt. Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.

  ```dotnetcli
  dotnet new ng
  ```

- Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:

  ```dotnetcli
  dotnet new -u
  ```

- Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a>Siehe auch

- [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md)
- [Erstellen eines benutzerdefinierten Vorlagen-Assistenten](../tutorials/cli-templates-create-item-template.md)
- [dotnet/dotnet-template-samples-GitHub-Repository](https://github.com/dotnet/dotnet-template-samples)
- [Verfügbare Vorlagen für dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
