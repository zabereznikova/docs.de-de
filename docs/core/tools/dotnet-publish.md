---
title: Befehl „dotnet publish“
description: Der Befehl „dotnet publish“ dient zum Veröffentlichen eines .NET Core-Projekts oder einer .NET Core-Projektmappe in einem Verzeichnis.
ms.date: 02/24/2020
ms.openlocfilehash: 61cfcf06586f3ac66526de69a17b8aef3cf0c795
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365582"
---
# <a name="dotnet-publish"></a>dotnet publish

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet publish` veröffentlicht die Anwendung und ihre Abhängigkeiten in einem Ordner für die Bereitstellung auf einem Hostsystem.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-p:PublishReadyToRun=true] [-p:PublishSingleFile=true] [-p:PublishTrimmed=true]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--self-contained [true|false]]
    [--no-self-contained] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

## <a name="description"></a>Beschreibung

`dotnet publish` kompiliert die Anwendung, liest ihre Abhängigkeiten, die in der Projektdatei angegeben sind, und veröffentlicht die resultierenden Dateien in einem Verzeichnis. Die Ausgabe umfasst die folgenden Objekte:

- Intermediate Language-Code (IL) in einer Assembly mit einer *DLL*-Erweiterung.
- Die Datei *.deps.json*, die alle Abhängigkeiten des Projekts enthält
- Die Datei *.runtimeconfig.json*, die die Shared Runtime, die von der Anwendung erwartet wird, sowie andere Konfigurationsoptionen für die Runtime festlegt (z. B. die Art der Garbage Collection).
- Die Abhängigkeiten der Anwendung, die aus dem NuGet-Cache in den Ausgabeordner kopiert werden.

Die Ausgabe des Befehls `dotnet publish` steht für die Bereitstellung zur Ausführung auf einem Hostsystem bereit (z.B. ein Server, Computer, Mac oder Laptop). Es ist die einzige offiziell unterstützte Methode zum Vorbereiten der Anwendung für die Bereitstellung. Je nach Art der Bereitstellung, die im Projekt angegeben ist, hat das Hostsystem die freigegebene .NET Core-Laufzeit installiert oder nicht. Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](../deploying/deploy-with-cli.md).

### <a name="implicit-restore"></a>Implizite Wiederherstellung

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

### <a name="msbuild"></a>MSBuild

Der Befehl `dotnet publish` ruft MSBuild auf, welches das `Publish`-Ziel aufruft. Alle Parameter, die an `dotnet publish` übergeben werden, werden an MSBuild übergeben. Die Parameter `-c` und `-o` verweisen auf die MSBuild-Eigenschaften `Configuration` bzw. `PublishDir`.

Der `dotnet publish`-Befehl akzeptiert MSBuild-Optionen, z. B. `-p` zum Festlegen von Eigenschaften oder `-l` zum Definieren eines Protokolls. Beispielsweise können Sie eine MSBuild-Eigenschaft mit dem folgenden Format festlegen: `-p:<NAME>=<VALUE>`. Sie können auch Veröffentlichungseigenschaften festlegen, indem Sie auf eine *PUBXML*-Datei verweisen, wie z. B. in der folgenden Codezeile:

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference)
- [Visual Studio-Veröffentlichungsprofile (PUBXML) für die Bereitstellung von ASP.NET Core-Apps](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)

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

  Gibt den Pfad für das Ausgabeverzeichnis an.
  
  Wenn diese Option nicht angegeben wird, wird für runtimeabhängige ausführbare Dateien und plattformübergreifende Binärdateien standardmäßig *[Projektdateiordner]./bin/[Konfiguration]/[Framework]/publish/* verwendet. Für eigenständige ausführbare Dateien wird standardmäßig *[Projektdateiordner]./bin/[Konfiguration]/[Framework]/[Runtime]/publish/* verwendet.

  In einem Webprojekt führen aufeinanderfolgende `dotnet publish`-Befehle zu geschachtelten Ausgabeordnern, wenn sich der Ausgabeordner im Projektordner befindet. Wenn der Projektordner beispielsweise *MeinProjekt* lautet und als Ausgabeordner *MeinProjekt/publish* festgelegt ist, werden bei zweimaliger Ausführung von `dotnet publish` die Inhaltsdateien (beispielsweise die *CONFIG*- und *JSON*-Dateien) der zweiten Ausführung in *MeinProjekt/publish/publish* platziert. Um eine Schachtelung der Veröffentlichungsordner zu vermeiden, geben Sie einen Ordner für die Veröffentlichung an, der sich nicht **direkt** unter dem Projektordner befindet. Alternativ können Sie den Veröffentlichungsordner aus dem Projekt ausschließen. Um einen Veröffentlichungsordner namens *publishoutput* auszuschließen, fügen Sie das folgende Element einem `PropertyGroup`-Element in der *CSPROJ*-Datei hinzu:

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - .NET Core 3. x SDK und höher
  
    Wenn beim Veröffentlichen eines Projekts ein relativer Pfad angegeben wird, ist das generierte Ausgabeverzeichnis relativ zum aktuellen Arbeitsverzeichnis statt zum Speicherort der Projektdatei.

    Wenn beim Veröffentlichen einer Projektmappe ein relativer Pfad angegeben wird, werden alle Ausgaben für sämtliche Projekte im angegebenen Ordner relativ zum aktuellen Arbeitsverzeichnis gespeichert. Um die Veröffentlichungsausgabe in eigenen Ordnern für jedes Projekt zu speichern, geben Sie einen relativen Pfad an, indem Sie die MSBuild-`PublishDir`-Eigenschaft anstelle der `--output`-Option verwenden. Beispielsweise wird mit `dotnet publish -p:PublishDir=.\publish` die Veröffentlichungsausgabe für jedes Projekt an den Ordner `publish` unter dem Ordner gesendet, der die Projektdatei enthält.

  - .NET Core 2.x SDK
  
    Wenn beim Veröffentlichen eines Projekts ein relativer Pfad angegeben wird, ist das generierte Ausgabeverzeichnis relativ zum Speicherort der Projektdatei statt zum aktuellen Arbeitsverzeichnis.

    Wenn beim Veröffentlichen einer Projektmappe ein relativer Pfad angegeben wird, wird die Ausgabe jedes Projekts in einem eigenen Ordner relativ zum Speicherort der Projektdatei gespeichert. Wenn beim Veröffentlichen einer Projektmappe ein absoluter Pfad angegeben wird, werden alle Veröffentlichungsausgaben für alle Projekte im angegebenen Ordner gespeichert.

- **`-p:PublishReadyToRun=true`**

  Kompiliert Anwendungsassemblys im R2R-Format (ReadyToRun). R2R ist eine Form der AOT-Kompilierung (Ahead-Of-Time). Weitere Informationen finden Sie unter [ReadyToRun-Images](../whats-new/dotnet-core-3-0.md#readytorun-images). Verfügbar seit .NET Core 3.0 SDK.

  Es wird empfohlen, diese Option nicht auf der Befehlszeile, sondern in einem Veröffentlichungsprofil anzugeben. Weitere Informationen finden Sie unter [MSBuild](#msbuild).

- **`-p:PublishSingleFile=true`**

  Packt die App in einer plattformspezifischen ausführbaren Einzeldatei. Die ausführbare Datei ist selbstextrahierend und enthält alle Abhängigkeiten (einschließlich der nativen), die zum Ausführen der App erforderlich sind. Beim ersten Ausführen der App wird die Anwendung in ein Verzeichnis extrahiert, das auf dem Namen und dem Buildbezeichner der App basiert. Der Start ist beim erneuten Ausführen der App schneller. Die Anwendung muss sich nicht selbst ein zweites Mal extrahieren, sofern keine neue Version verwendet wird. Verfügbar seit .NET Core 3.0 SDK.

  Weitere Informationen zum Veröffentlichen einzelner Dateien finden Sie im [Einzeldatei-Bundler-Entwurfsdokument](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).

  Es wird empfohlen, diese Option nicht auf der Befehlszeile, sondern in einem Veröffentlichungsprofil anzugeben. Weitere Informationen finden Sie unter [MSBuild](#msbuild).

- **`-p:PublishTrimmed=true`**

  Kürzt nicht verwendete Bibliotheken, um die Bereitstellungsgröße einer App zu verringern, wenn diese als selbstextrahierende ausführbare Datei veröffentlicht wird. Weitere Informationen finden Sie unter [Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien](../deploying/trim-self-contained.md). Verfügbar seit .NET Core 3.0 SDK.

  Es wird empfohlen, diese Option nicht auf der Befehlszeile, sondern in einem Veröffentlichungsprofil anzugeben. Weitere Informationen finden Sie unter [MSBuild](#msbuild).

- **`--self-contained [true|false]`**

  Veröffentlicht die .NET Core-Runtime mit Ihrer Anwendung, sodass die Runtime nicht auf dem Zielcomputer installiert werden muss. Der Standardwert ist `true`, wenn ein Laufzeitbezeichner angegeben wird und das Projekt ein ausführbares Projekt (kein Bibliotheksprojekt) ist. Weitere Informationen finden Sie unter [Veröffentlichen von .NET Core-Anwendungen](../deploying/index.md) und [Veröffentlichen von .NET Core-Apps mit der .NET Core-CLI](../deploying/deploy-with-cli.md).

  Wenn diese Option verwendet wird, ohne `true` oder `false` anzugeben, ist der Standardwert `true`. Fügen Sie in diesem Fall das Projektmappen- oder Projektargument nicht unmittelbar nach `--self-contained` ein, da an dieser Position `true` oder `false` erwartet wird.

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
- [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference)
- [Visual Studio-Veröffentlichungsprofile (PUBXML) für die Bereitstellung von ASP.NET Core-Apps](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)
- [ILLInk.Tasks](https://aka.ms/dotnet-illink)
