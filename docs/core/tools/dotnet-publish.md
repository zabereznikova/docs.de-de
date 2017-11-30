---
title: "dotnet publish-Befehl – .NET Core-CLI"
description: "Der „dotnet publish“-Befehl veröffentlicht ein .NET Core-Projekt in einem Verzeichnis."
author: mairaw
ms.author: mairaw
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: d59ba8cf74a63c7d4a2234989477b5778fa0148f
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-publish"></a>dotnet publish

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet publish`: Packt die Anwendung und ihre Abhängigkeiten in einen Ordner für die Bereitstellung auf einem Hostsystem.

## <a name="synopsis"></a>Übersicht

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. Die Ausgabe wird Folgendes enthalten:

* Intermediate Language-Code (IL) in einer Assembly mit einer *DLL*-Erweiterung.
* *deps.json*-Datei, die alle Abhängigkeiten des Projekts enthält.
* Eine *.runtime.config.json*-Datei, die die freigegebene Laufzeit angibt, die die Anwendung erwartet, sowie andere Konfigurationsoptionen für die Laufzeit (z.B. Typ der automatischen Speicherbereinigung).
* Die Abhängigkeiten der Anwendung. Diese werden aus dem NuGet-Cache in den Ausgabeordner kopiert.

Die `dotnet publish`-Ausgabe des Befehls ist bereit für die Bereitstellung auf einem Hostsystem (z.B. ein Server, PC, Mac, Laptops) für die Ausführung und ist der einzige offiziell unterstützte Weg, um die Anwendung für die Bereitstellung vorzubereiten. Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht. Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../deploying/index.md). Die Verzeichnisstruktur der veröffentlichten Anwendung finden Sie unter [Directory structure (Verzeichnisstruktur)](/aspnet/core/hosting/directory-structure).

## <a name="arguments"></a>Argumente

`PROJECT`

Das zu veröffentlichende Projekt – standardmäßig das aktuelle Verzeichnis, wenn nicht angegeben.

## <a name="options"></a>Optionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md). Sie müssen das Zielframework in der Projektdatei angeben.

`--force`

Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dies entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--manifest <PATH_TO_MANIFEST_FILE>`

Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken. Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md). Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu. Diese Option ist am dem .NET Core 2.0 SDK verfügbar.

`--no-dependencies`

Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.

`--no-restore`

Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird

`-o|--output <OUTPUT_DIRECTORY>`

Gibt den Pfad für das Ausgabeverzeichnis an. Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]* für eine eigenständige Bereitstellung gewählt.
Wenn ein relativer Pfad angegeben wird, ist das Ausgabeverzeichnis generiert relativ zum Speicherort Projekts-Datei nicht in das aktuelle Arbeitsverzeichnis.

`--self-contained`

Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss. Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`. Weitere Informationen zu anderen Bereitstellungstypen finden Sie unter [.NET Core-anwendungsbereitstellung](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet. Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md). Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.

`-v|--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Legt die Buildkonfiguration fest. Der Standardwert ist `Debug`.

`-f|--framework <FRAMEWORK>`

Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md). Sie müssen das Zielframework in der Projektdatei angeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--manifest <PATH_TO_MANIFEST_FILE>`

Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken. Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md). Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu. Diese Option ist am dem .NET Core 2.0 SDK verfügbar.

`-o|--output <OUTPUT_DIRECTORY>`

Gibt den Pfad für das Ausgabeverzeichnis an. Wenn nicht angegeben, wird standardmäßig *./bin/[configuration]/[framework]/* für eine Framework-abhängige Bereitstellung oder *./bin/[configuration]/[framework]/[runtime]* für eine eigenständige Bereitstellung gewählt.
Wenn ein relativer Pfad angegeben wird, ist das Ausgabeverzeichnis generiert relativ zum Speicherort Projekts-Datei nicht in das aktuelle Arbeitsverzeichnis.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Wird bei der Erstellung einer [eigenständigen Bereitstellung (Self-contained deployments, SCD)](../deploying/index.md#self-contained-deployments-scd) verwendet. Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md). Standardmäßig wird eine [Framework-abhängige Bereitstellung (FDD)](../deploying/index.md#framework-dependent-deployments-fdd) veröffentlicht.

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

## <a name="see-also"></a>Siehe auch

* [Zielframeworks](../../standard/frameworks.md)
* [Runtime-ID-Katalog (RID)](../rid-catalog.md)
