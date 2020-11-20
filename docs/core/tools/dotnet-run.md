---
title: Befehl „dotnet run“
description: Der dotnet run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode.
ms.date: 02/19/2020
ms.openlocfilehash: c80f290c75e3bac65ae73fe8edada53db4ce86f8
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634415"
---
# <a name="dotnet-run"></a>dotnet run

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet run [-c|--configuration <CONFIGURATION>] [-f|--framework <FRAMEWORK>]
    [--force] [--interactive] [--launch-profile <NAME>] [--no-build]
    [--no-dependencies] [--no-launch-profile] [--no-restore]
    [-p|--project <PATH>] [-r|--runtime <RUNTIME_IDENTIFIER>]
    [-v|--verbosity <LEVEL>] [[--] [application arguments]]

dotnet run -h|--help
```

## <a name="description"></a>Beschreibung

Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl. Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile. Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen. Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet.

Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben. Angenommen, Sie haben eine `netcoreapp2.1`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp2.1` platziert. Dateien werden bei Bedarf überschrieben. Temporäre Dateien befinden sich im `obj`-Verzeichnis.

Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.

Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys. Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden. Zum Ausführen von `myapp.dll` verwenden Sie z.B.:

```dotnetcli
dotnet myapp.dll
```

Weitere Informationen zum `dotnet`-Treiber finden Sie unter [.NET-Befehlszeilentools (CLI)](index.md).

Der Befehl `dotnet run` löst die Abhängigkeiten der Anwendungen außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache, um die Anwendung auszuführen. Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden. Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit.

### <a name="implicit-restore"></a>Implizite Wiederherstellung

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a>Optionen

- **`--`**

  Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab. Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.

- **`-c|--configuration <CONFIGURATION>`**

  Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.

- **`-f|--framework <FRAMEWORK>`**

  Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus. Das Framework muss in der Projektdatei angegeben werden.

- **`--force`**

  Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen). Verfügbar seit .NET Core 3.0 SDK.

- **`--launch-profile <NAME>`**

  Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden). Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`. Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).

- **`--no-build`**

  Erstellt das Projekt nicht vor der Ausführung. Das `--no-restore`-Flag wird implizit festgelegt.

- **`--no-dependencies`**

  Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

- **`--no-launch-profile`**

  Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.

- **`--no-restore`**

  Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

- **`-p|--project <PATH>`**

  Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad). Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Die Kurzoption `-r` ist ab .NET Core 3.0 SDK verfügbar.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `m`. Verfügbar ab .NET Core 2.1 SDK.

## <a name="examples"></a>Beispiele

- Führt das Projekt im aktuellen Verzeichnis aus:

  ```dotnetcli
  dotnet run
  ```

- Führt das angegebene Projekt aus:

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da die leere Option `--` verwendet wird):

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- Stellt Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis wieder her, wobei nur eine minimale Ausgabe angezeigt wird, und führt das Projekt dann aus:

  ```dotnetcli
  dotnet run --verbosity m
  ```
