---
title: Befehl „dotnet run“
description: Der dotnet run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode.
ms.date: 10/31/2019
ms.openlocfilehash: 87e9a57e874116533951a9c5eb676be76be2c98d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454778"
---
# <a name="dotnet-run"></a>dotnet run

**Dieser Artikel gilt für: ✓**.NET Core 1.x SDK und spätere Versionen

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.

## <a name="synopsis"></a>Übersicht

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a>BESCHREIBUNG

Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl. Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile. Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen. Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet.

Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben. Angenommen, Sie haben eine `netcoreapp2.1`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp2.1` platziert. Dateien werden bei Bedarf überschrieben. Temporäre Dateien befinden sich im `obj`-Verzeichnis.

Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.

Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys. Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden. Zum Ausführen von `myapp.dll` verwenden Sie z.B.:

```dotnetcli
dotnet myapp.dll
```

Weitere Informationen zum `dotnet`-Treiber finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).

Der Befehl `dotnet run` löst die Abhängigkeiten der Anwendungen außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache, um die Anwendung auszuführen. Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden. Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a>Optionen

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

`--`

Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`.

`-f|--framework <FRAMEWORK>`

Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus. Das Framework muss in der Projektdatei angegeben werden.

`--force`

Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--interactive`

Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).

`--launch-profile <NAME>`

Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden). Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`. Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).

`--no-build`

Erstellt das Projekt nicht vor der Ausführung. Das `--no-restore`-Flag wird implizit festgelegt.

`--no-dependencies`

Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

`--no-launch-profile`

Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.

`--no-restore`

Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

`-p|--project <PATH>`

Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad). Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.

`--runtime <RUNTIME_IDENTIFIER>`

Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--`

Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`.

`-f|--framework <FRAMEWORK>`

Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus. Das Framework muss in der Projektdatei angegeben werden.

`--force`

Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--launch-profile <NAME>`

Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden). Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`. Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).

`--no-build`

Erstellt das Projekt nicht vor der Ausführung. Das `--no-restore`-Flag wird implizit festgelegt.

`--no-dependencies`

Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

`--no-launch-profile`

Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.

`--no-restore`

Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

`-p|--project <PATH>`

Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad). Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.

`--runtime <RUNTIME_IDENTIFIER>`

Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--`

Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`.

`-f|--framework <FRAMEWORK>`

Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus. Das Framework muss in der Projektdatei angegeben werden.

`--force`

Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--launch-profile <NAME>`

Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden). Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`. Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).

`--no-build`

Erstellt das Projekt nicht vor der Ausführung. Das `--no-restore`-Flag wird implizit festgelegt.

`--no-dependencies`

Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

`--no-launch-profile`

Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.

`--no-restore`

Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

`-p|--project <PATH>`

Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad). Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.

`--runtime <RUNTIME_IDENTIFIER>`

Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--`

Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`.

`-f|--framework <FRAMEWORK>`

Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus. Das Framework muss in der Projektdatei angegeben werden.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`-p|--project <PATH/PROJECT.csproj>`

Gibt den Pfad und Namen der Projektdatei an. (Siehe HINWEIS.) Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.

> [!NOTE]
> Verwenden Sie den Pfad und Namen der Projektdatei mit der `-p|--project`-Option. Eine Regression in der CLI verhindert, dass ein Pfad mit dem .NET Core SDK 1.x bereitgestellt wird. Weitere Informationen zu diesem Problem finden Sie unter [dotnet run -p, can not start a project (dotnet/cli #5992) (dotnet run -p, ein Projekt kann nicht gestartet werden (dotnet/cli #5992))](https://github.com/dotnet/cli/issues/5992).

---

## <a name="examples"></a>Beispiele

Führt das Projekt im aktuellen Verzeichnis aus:

`dotnet run`

Führt das angegebene Projekt aus:

`dotnet run --project ./projects/proj1/proj1.csproj`

Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da die leere Option `--` verwendet wird):

`dotnet run --configuration Release -- --help`

Stellt Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis wieder her, wobei nur eine minimale Ausgabe angezeigt wird, und führt dann das Projekt aus (.NET Core SDK 2.0 und spätere Versionen):

`dotnet run --verbosity m`
