---
title: Tools für die .NET Core-Befehlszeilenschnittstelle (command-line interface, CLI)
description: Dies ist ein Überblick über die Tools und Funktionen der .NET Core-Befehlszeilenschnittstelle (Command-Line Interface, CLI).
ms.date: 08/14/2017
ms.openlocfilehash: b3bffb47ff973bd0da90e3f943e817756e563138
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714147"
---
# <a name="net-core-command-line-interface-cli-tools"></a>Tools für die .NET Core-Befehlszeilenschnittstelle (command-line interface, CLI)

Die .NET Core-Befehlszeilenschnittstelle (CLI) ist eine neue plattformübergreifende Toolkette zur Entwicklung von .NET-Anwendungen. Die CLI ist eine Grundlage, auf der Tools höherer Ebene wie z.B. integrierte Entwicklungsumgebungen (Integrated Development Environments, IDEs), Editoren und Build-Koordinatoren aufbauen können.

## <a name="installation"></a>Installation

Verwenden Sie entweder die nativen Installer oder die Installations-Shellskripts:

- Die nativen Installer werden vor allem auf Entwicklercomputern verwendet und verwenden den nativen Installationsmechanismus der jeweiligen unterstützten Plattform, z.B. DEB-Pakete unter Ubuntu oder MSI-Bündel unter Windows. Diese Installer installieren und konfigurieren die Umgebung für sofortige Verwendung durch den Entwickler, erfordern jedoch Administratorrechte auf dem Computer. Die Installationsanweisungen finden Sie im [.NET Core-Installationshandbuch](https://aka.ms/dotnetcoregs).
- Shellskripts werden hauptsächlich für die Einrichtung von Buildservern verwendet, oder wenn Sie die Tools ohne Administratorrechte installieren möchten. Installationsskripts installieren keine erforderlichen Komponenten auf dem Computer, diese müssen manuell installiert werden. Weitere Informationen finden Sie unter [install script reference (Referenz zu Installationsskripts)](dotnet-install-script.md). Informationen zum Einrichten der CLI auf dem Buildserver der fortlaufenden Integration (Continuous Integration, CI) finden Sie unter [Verwenden des .NET Core SDK und der entsprechenden Tools in Continuous Integration (CI)](using-ci-with-cli.md).

Standardmäßig installiert die CLI in paralleler Ausführung (side-by-side, SxS), sodass mehrere Versionen der CLI-Tools auf einem einzelnen Computer gleichzeitig vorhanden sein können. Wie bestimmt wird, welche Version auf einem Computer verwendet wird, auf dem mehrere Versionen installiert sind, wird im Abschnitt [Treiber](#driver) ausführlicher erklärt.

## <a name="cli-commands"></a>CLI-Befehle

Die folgenden Befehle werden standardmäßig erstellt:

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Grundlegende Befehle**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)
- [help](dotnet-help.md)
- [store](dotnet-store.md)

**Befehle zur Projektänderung**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**Erweiterte Befehle**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Grundlegende Befehle**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)

**Befehle zur Projektänderung**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**Erweiterte Befehle**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

---

Die CLI übernimmt ein Erweiterbarkeitsmodell, mit dem Sie zusätzliche Tools für Ihre Projekte angeben können. Weitere Informationen finden Sie im Thema [.NET Core CLI extensibility model (.NET Core-CLI-Erweiterbarkeitsmodell)](extensibility.md).

## <a name="command-structure"></a>Befehlsstruktur

Die CLI-Befehlsstruktur besteht aus dem [Treiber („dotnet“)](#driver), dem [Befehl](#command) und möglicherweise aus [Argumenten](#arguments) und [Optionen](#options). Sie sehen dieses Muster in den meisten CLI-Vorgängen wie z.B. beim Erstellen einer neuen Konsolenanwendung und deren Ausführung von der Befehlszeile aus, wie die folgenden Befehle zeigen, wenn sie aus einem Verzeichnis mit dem Namen *my_app* ausgeführt werden:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a>Treiber

Der Treiber trägt den Namen [dotnet](dotnet.md) und hat zwei Aufgaben, entweder die Ausführung einer [Framework-abhängigen Anwendung](../deploying/index.md) oder die Ausführung eines Befehls. 

Geben Sie zur Ausführung einer Framework-abhängigen Anwendung nach dem Treiber die Anwendung an, z.B. `dotnet /path/to/my_app.dll`. Führen Sie beim Ausführen des Befehls aus dem Ordner, in dem sich die DLL der Anwendung befindet, einfach `dotnet my_app.dll` aus. Wenn Sie eine bestimmte Version der .NET Core-Runtime verwenden möchten, verwenden Sie die `--fx-version <VERSION>`-Option (weitere Informationen dazu finden Sie in der [Referenz zum dotnet-Befehl](dotnet.md)).

Wenn Sie einen Befehl an den Treiber geben, startet `dotnet.exe` den Ausführungsprozess des CLI-Befehls. Zum Beispiel:

```dotnetcli
dotnet build
```

Zunächst bestimmt der Treiber die zu verwendende SDK-Version. Wenn keine [„global.json“](global-json.md)-Datei vorhanden ist, wird die neueste Version des verfügbaren SDK verwendet. Dabei handelt es sich entweder um eine Vorschauversion oder eine stabile Version, je nachdem, welche Version sich aktuell auf dem Computer befindet.  Sobald die SDK-Version bestimmt ist, wird der Befehl ausgeführt.

### <a name="command"></a>Befehl

Über den Befehl wird eine Aktion durchgeführt. Beispielsweise erstellt der Befehl `dotnet build` Code und der Befehl `dotnet publish` veröffentlicht Code. Die Befehle werden mit einer `dotnet {command}`-Konvention als Konsolenanwendung implementiert.

### <a name="arguments"></a>Argumente

Die Argumente, die Sie in der Befehlszeile übergeben, sind die Argumente für den aufgerufenen Befehl. Wenn Sie z.B. `dotnet publish my_app.csproj` ausführen, gibt das `my_app.csproj`-Argument das zu veröffentlichende Projekt an und wird an den `publish`-Befehl übergeben.

### <a name="options"></a>Optionen

Die Optionen, die Sie in der Befehlszeile übergeben, sind die Optionen für den aufgerufenen Befehl. Wenn Sie z.B. `dotnet publish --output /build_output` ausführen, werden die `--output`-Option und ihr Wert an den `publish`-Befehl übergeben.

## <a name="migration-from-projectjson"></a>Migration von project.json

Wenn Sie Preview 2-Tools verwendet haben, um *project.json*-basierte Projekte zu erzeugen, finden Sie im Thema [dotnet-migrate](dotnet-migrate.md) Informationen zur Migration eines Projekts zu MSBuild/ *.csproj* für die Verwendung mit Versionstools. Aktualisieren Sie für .NET Core-Projekte, die vor der Veröffentlichung der Vorschau 2-Tools erstellt wurden, das Projekt entweder manuell anhand der Anweisungen in [Migrieren von DNX zur .NET Core-CLI (project.json)](../migration/from-dnx.md) und verwenden dann `dotnet migrate`, oder führen Sie direkt ein Upgrade für die Projekte durch.

## <a name="see-also"></a>Siehe auch

- [dotnet/CLI GitHub Repository (dotnet/CLI-GitHub-Repository)](https://github.com/dotnet/cli/)
- [.NET Core installation guide (.NET Core-Installationshandbuch)](https://aka.ms/dotnetcoregs)
