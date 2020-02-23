---
title: Befehl „dotnet publish“
description: Der „dotnet publish“-Befehl veröffentlicht ein .NET Core-Projekt in einem Verzeichnis.
ms.date: 05/29/2018
ms.openlocfilehash: 0653a7b1e1abd6d7ffd3d21a0410279235b43a28
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451291"
---
# <a name="dotnet-publish"></a>dotnet publish

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet publish`: Packt die Anwendung und ihre Abhängigkeiten in einen Ordner für die Bereitstellung auf einem Hostsystem.

## <a name="synopsis"></a>Übersicht

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. Die Ausgabe umfasst die folgenden Objekte:

- Intermediate Language-Code (IL) in einer Assembly mit einer *DLL*-Erweiterung.
- *.deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält.
- Eine Datei vom Typ *.runtimeconfig.json*, die die von der Anwendung erwartete freigegebene Laufzeit sowie andere Konfigurationsoptionen für die Laufzeit angibt (etwa die Art der Garbage Collection).
- Die Abhängigkeiten der Anwendung, die aus dem NuGet-Cache in den Ausgabeordner kopiert werden.

Die Ausgabe des Befehls `dotnet publish` steht für die Bereitstellung zur Ausführung auf einem Hostsystem bereit (z.B. ein Server, Computer, Mac oder Laptop). Es ist die einzige offiziell unterstützte Methode zum Vorbereiten der Anwendung für die Bereitstellung. Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht. Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md). Die Verzeichnisstruktur der veröffentlichten Anwendung finden Sie unter [Directory structure (Verzeichnisstruktur)](/aspnet/core/hosting/directory-structure).

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argumente

`PROJECT`

Das zu veröffentlichende Projekt. Dies ist entweder der Pfad und der Dateiname einer [C#](csproj.md)-, F#- oder Visual Basic-Projektdatei oder der Pfad zu einem Verzeichnis mit einer C#-, F#- oder Visual Basic-Projektdatei. Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.

## <a name="options"></a>Optionen

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md). Sie müssen das Zielframework in der Projektdatei angeben.

`--force`

Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--manifest <PATH_TO_MANIFEST_FILE>`

Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken. Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md). Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu. Diese Option ist am dem .NET Core 2.0 SDK verfügbar.

`--no-build`

Erstellt das Projekt nicht vor der Veröffentlichung. Zudem wird das Flag `--no-restore` implizit festgelegt.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.

`--no-restore`

Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

`-o|--output <OUTPUT_DIRECTORY>`

Gibt den Pfad für das Ausgabeverzeichnis an. Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.
Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.

`--self-contained`

Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss. Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`. Weitere Informationen zu den verschiedenen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#publish-self-contained) verwendet. Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md). Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#publish-runtime-dependent) veröffentlicht.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md). Sie müssen das Zielframework in der Projektdatei angeben.

`--force`

Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--manifest <PATH_TO_MANIFEST_FILE>`

Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken. Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md). Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu. Diese Option ist am dem .NET Core 2.0 SDK verfügbar.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.

`--no-restore`

Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

`-o|--output <OUTPUT_DIRECTORY>`

Gibt den Pfad für das Ausgabeverzeichnis an. Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.
Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.

`--self-contained`

Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss. Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`. Weitere Informationen zu den verschiedenen Bereitstellungstypen finden Sie unter [.NET Core application deployment (Bereitstellung von .NET Core-Anwendungen)](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#publish-self-contained) verwendet. Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md). Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#publish-runtime-dependent) veröffentlicht.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md). Sie müssen das Zielframework in der Projektdatei angeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--manifest <PATH_TO_MANIFEST_FILE>`

Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken. Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md). Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu. Diese Option ist am dem .NET Core 2.0 SDK verfügbar.

`-o|--output <OUTPUT_DIRECTORY>`

Gibt den Pfad für das Ausgabeverzeichnis an. Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]/publish/* für eine eigenständige Bereitstellung gewählt.
Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#publish-self-contained) verwendet. Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md). Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#publish-runtime-dependent) veröffentlicht.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.

---

## <a name="examples"></a>Beispiele

Veröffentlicht das Projekt im aktuellen Verzeichnis:

`dotnet publish`

Veröffentlichen Sie die Anwendung unter Verwendung der angegebenen Projektdatei:

`dotnet publish ~/projects/app1/app1.csproj`

Veröffentlichen Sie das Projekt aus dem aktuellen Verzeichnis unter Verwendung des `netcoreapp1.1`-Frameworks:

`dotnet publish --framework netcoreapp1.1`

Veröffentlichen der aktuellen Anwendung mithilfe des `netcoreapp1.1`-Frameworks und der Laufzeit für `OS X 10.10` (Sie müssen diese RID in der Projektdatei auflisten).

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

Veröffentlichen sie die aktuelle Anwendung, aber fügen Sie während der Wiederherstellung keine Projekt-zu-Projekt-Verweise hinzu, sondern nur das Stammprojekt (.NET Core SDK 2.0 und spätere Versionen):

`dotnet publish --no-dependencies`

## <a name="see-also"></a>Siehe auch

- [Zielframeworks](../../standard/frameworks.md)
- [Runtime-ID-Katalog (RID)](../rid-catalog.md)
