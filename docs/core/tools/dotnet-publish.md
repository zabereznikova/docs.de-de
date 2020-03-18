---
title: Befehl „dotnet publish“
description: Der Befehl „dotnet publish“ dient zum Veröffentlichen eines .NET Core-Projekts oder einer .NET Core-Projektmappe in einem Verzeichnis.
ms.date: 02/24/2020
ms.openlocfilehash: c34618409c9a539043c84c7e03daa8aa249d64f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146554"
---
# <a name="dotnet-publish"></a>dotnet publish

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet publish` veröffentlicht die Anwendung und ihre Abhängigkeiten in einem Ordner für die Bereitstellung auf einem Hostsystem.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. Die Ausgabe umfasst die folgenden Objekte:

- Intermediate Language-Code (IL) in einer Assembly mit einer *DLL*-Erweiterung.
- Die Datei *.deps.json*, die alle Abhängigkeiten des Projekts enthält
- Die Datei *.runtimeconfig.json*, die die Shared Runtime, die von der Anwendung erwartet wird, sowie andere Konfigurationsoptionen für die Runtime festlegt (z. B. die Art der Garbage Collection).
- Die Abhängigkeiten der Anwendung, die aus dem NuGet-Cache in den Ausgabeordner kopiert werden.

Die Ausgabe des Befehls `dotnet publish` steht für die Bereitstellung zur Ausführung auf einem Hostsystem bereit (z.B. ein Server, Computer, Mac oder Laptop). Es ist die einzige offiziell unterstützte Methode zum Vorbereiten der Anwendung für die Bereitstellung. Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht.

## <a name="arguments"></a>Argumente

- **`PROJECT|SOLUTION`**

  Das Projekt bzw. die Projektmappe, die veröffentlicht werden soll.
  
  * `PROJECT` ist der Pfad und Dateiname einer [C#](csproj.md)-, F#- oder Visual Basic-Projektdatei, oder der Pfad zu einem Verzeichnis, das eine C#-, F#- oder Visual Basic-Projektdatei enthält. Wenn das Verzeichnis nicht angegeben wird, wird standardmäßig das aktuelle Verzeichnis verwendet.

  * `SOLUTION` ist der Pfad und Dateiname einer Projektmappendatei (mit der Erweiterung *.sln*), oder der Pfad zu einem Verzeichnis, das eine Projektmappendatei enthält. Wenn das Verzeichnis nicht angegeben wird, wird standardmäßig das aktuelle Verzeichnis verwendet. Verfügbar seit .NET Core 3.0 SDK.

## <a name="options"></a>Optionen

- **`-c|--configuration <CONFIGURATION>`**

  Legt die Buildkonfiguration fest. Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.

- **`-f|--framework <FRAMEWORK>`**

  Veröffentlicht die Anwendung für das angegebene [Zielframework](../../standard/frameworks.md). Sie müssen das Zielframework in der Projektdatei angeben.

- **`--force`**

  Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten. Beispielsweise, um die Authentifizierung abzuschließen. Verfügbar seit .NET Core 3.0 SDK.

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  Gibt mindestens ein [Zielmanifest](../deploying/runtime-store.md) an, das verwendet wird, um die Menge an mit der App veröffentlichten Paketen zu senken. Die Manifestdatei ist Teil der Ausgabe des [`dotnet store`-Befehls](dotnet-store.md). Um mehrere Manifeste anzugeben, fügen Sie die `--manifest`-Option für jedes Manifest hinzu.

- **`--no-build`**

  Erstellt das Projekt nicht vor der Veröffentlichung. Zudem wird das Flag `--no-restore` implizit festgelegt.

- **`--no-dependencies`**

  Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.

- **`--nologo`**

  Unterdrückt die Anzeige von Startbanner und Copyrightmeldung. Verfügbar seit .NET Core 3.0 SDK.

- **`--no-restore`**

  Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Gibt den Pfad für das Ausgabeverzeichnis an. Wenn diese Option nicht angegeben wird, wird standardmäßig *./bin/[configuration]/[framework]/publish/* für runtime-abhängige ausführbare Dateien und plattformübergreifende Binärdateien verwendet. Für eigenständige ausführbare Dateien wird standardmäßig *./bin/[configuration]/[framework]/[runtime]/publish/* verwendet.

  Bei einem relativen Pfad ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei anstatt zum aktuellen Arbeitsverzeichnis.

- **`--self-contained [true|false]`**

  Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss. Wenn ein Runtimebezeichner angegeben ist, ist der Standardwert `true`. Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Anwendungen](../deploying/index.md) und [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](../deploying/deploy-with-cli.md).

- **`--no-self-contained`**

  Entspricht `--self-contained false`. Verfügbar seit .NET Core 3.0 SDK.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Veröffentlicht die Anwendung für eine bestimmte Laufzeit. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Anwendungen](../deploying/index.md) und [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](../deploying/deploy-with-cli.md).

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `minimal`sein.

- **`--version-suffix <VERSION_SUFFIX>`**

  Definiert das Versionssuffix zum Ersetzen des Sternchens (`*`) im Versionsfeld der Projektdatei.

## <a name="examples"></a>Beispiele

- Erstellen Sie eine [runtime-abhängige plattformübergreifende Binärdatei](../deploying/index.md#produce-a-cross-platform-binary) für das Projekt im aktuellen Verzeichnis:

  ```dotnetcli
  dotnet publish
  ```

  Ab .NET Core 3.0 SDK wird mit diesem Beispielbefehl auf eine [runtime-abhängige ausführbare Datei](../deploying/index.md#publish-runtime-dependent) für die aktuelle Plattform erstellt.

- Erstellen Sie für das Projekt im aktuellen Verzeichnis eine [eigenständige ausführbare Datei](../deploying/index.md#publish-self-contained) für eine spezifische Runtime:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  Die RID muss in der Projektdatei enthalten sein.

- Erstellen Sie für das Projekt im aktuellen Verzeichnis eine [runtime-abhängige ausführbare Datei](../deploying/index.md#publish-runtime-dependent) für eine spezifische Plattform:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  Die RID muss in der Projektdatei enthalten sein. Dieses Beispiel gilt für .NET Core 3.0 SDK und höher.

- Veröffentlichen Sie das Projekt im aktuellen Verzeichnis für eine spezifische Runtime und ein spezifisches Zielframework:

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- Veröffentlichen Sie die angegebene Projektdatei:

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- Veröffentlichen sie die aktuelle Anwendung, aber fügen Sie während der Wiederherstellung keine Projekt-zu-Projekt-Verweise hinzu, sondern nur das Stammprojekt:

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a>Siehe auch

- [Übersicht über die .NET Core-Anwendungsveröffentlichung](../deploying/index.md)
- [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](../deploying/deploy-with-cli.md)
- [Zielframeworks](../../standard/frameworks.md)
- [Runtime-ID-Katalog (RID)](../rid-catalog.md)
- [Verwenden der macOS Catalina-Notarisierung](../install/macos-notarization-issues.md)
- [Verzeichnisstruktur einer veröffentlichten Anwendung](/aspnet/core/hosting/directory-structure)
