---
title: .NET Core-CLI
titleSuffix: ''
description: Eine Übersicht über die .NET Core-CLI und ihre Features.
ms.date: 02/13/2020
ms.openlocfilehash: 1078d68ddc088274fa14b0094a81765f7af69dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543313"
---
# <a name="net-core-cli-overview"></a>Übersicht über die .NET Core-CLI

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

Die .NET Core-Befehlszeilenschnittstelle (CLI) ist eine plattformübergreifende Toolkette zum Entwicklung, Erstellen, Ausführen und Veröffentlichen von .NET Core-Anwendungen.

Die .NET Core-CLI ist im [.NET Core SDK](../sdk.md) enthalten. Informationen zum Installieren des .NET Core SDK finden Sie unter [Installieren des .NET Core SDK](../install/sdk.md).

## <a name="cli-commands"></a>CLI-Befehle

Die folgenden Befehle werden standardmäßig erstellt:

### <a name="basic-commands"></a>Grundlegende Befehle

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

### <a name="project-modification-commands"></a>Befehle zur Projektänderung

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

### <a name="advanced-commands"></a>Erweiterte Befehle

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

### <a name="tool-management-commands"></a>Befehle für die Toolverwaltung

- [tool install](dotnet-tool-install.md)
- [tool list](dotnet-tool-list.md)
- [tool update](dotnet-tool-update.md)
- [tool restore](global-tools.md#install-a-local-tool) **Verfügbar ab .NET Core SDK 3.0**
- [tool run](global-tools.md#invoke-a-local-tool) **Verfügbar ab .NET Core SDK 3.0**
- [tool uninstall](dotnet-tool-uninstall.md)

Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden. Sie können Tools selbst schreiben oder Drittanbietertools installieren. Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet. Weitere Informationen finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).

## <a name="command-structure"></a>Befehlsstruktur

Die CLI-Befehlsstruktur besteht aus dem [Treiber („dotnet“)](#driver), dem [Befehl](#command) und möglicherweise aus [Argumenten](#arguments) und [Optionen](#options). Sie sehen dieses Muster in den meisten CLI-Vorgängen wie z.B. beim Erstellen einer neuen Konsolenanwendung und deren Ausführung von der Befehlszeile aus, wie die folgenden Befehle zeigen, wenn sie aus einem Verzeichnis mit dem Namen *my_app* ausgeführt werden:

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

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

## <a name="see-also"></a>Siehe auch

- [GitHub-Repository „dotnet/sdk“](https://github.com/dotnet/sdk/)
- [.NET Core installation guide (.NET Core-Installationshandbuch)](../install/sdk.md)
