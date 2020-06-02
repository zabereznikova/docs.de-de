---
title: Befehl „dotnet restore“
description: Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore.
ms.date: 02/27/2020
ms.openlocfilehash: 276fad896a6a8a647ed05a9de8c582d463d9ab8f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005315"
---
# <a name="dotnet-restore"></a>dotnet restore

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet restore [<ROOT>] [--configfile <FILE>] [--disable-parallel]
    [-f|--force] [--force-evaluate] [--ignore-failed-sources]
    [--interactive] [--lock-file-path <LOCK_FILE_PATH>] [--locked-mode]
    [--no-cache] [--no-dependencies] [--packages <PACKAGES_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [--use-lock-file] [-v|--verbosity <LEVEL>]

dotnet restore -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind.  In den meisten Fällen müssen Sie nicht explizit den Befehl `dotnet restore` verwenden, da eine NuGet-Wiederherstellung bei Bedarf implizit ausgeführt wird, wenn Sie die folgenden Befehle ausführen:

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

Manchmal kann es unpraktisch sein, die implizite NuGet-Wiederherstellung mit diesen Befehlen auszuführen. Zum Beispiel müssen einige automatisierte Systeme, wie etwa Buildsysteme, `dotnet restore` explizit aufrufen, um zu kontrollieren, wann die Wiederherstellung stattfindet, damit sie die Netzwerknutzung steuern können. Sie können das Flag `--no-restore` mit einem beliebigen dieser Befehle verwenden, um die implizite Wiederherstellung zu deaktivieren und eine implizite NuGet-Wiederherstellung zu verhindern.

### <a name="specify-feeds"></a>Angeben von Feeds

Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden. Feeds werden normalerweise über die *nuget.config*-Konfigurationsdatei bereitgestellt. Eine standardmäßige Konfigurationsdatei wird bereitgestellt, wenn das .NET Core SDK installiert sind. Führen Sie eine der folgenden Schritte durch, um zusätzliche Feeds anzugeben:

- Erstellen Sie eine eigene *nuget.config*-Datei im Projektverzeichnis. Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](/nuget/consume-packages/configuring-nuget-behavior) und unter [Unterschiede bei „nuget.config“](#nugetconfig-differences) weiter unten in diesem Artikel.
- Verwenden Sie `dotnet nuget`-Befehle wie [`dotnet nuget add source`](dotnet-nuget-add-source.md).

Sie können die *nuget.config-* -Feeds mit der `-s`-Option überschreiben.

Informationen zur Verwendung authentifizierter Feeds finden Sie unter [Nutzen von Paketen aus authentifizierten Feeds](/nuget/consume-packages/consuming-packages-authenticated-feeds).

### <a name="global-packages-folder"></a>Ordner für globale Pakete

Für Abhängigkeiten können Sie mithilfe des Arguments `--packages` angeben, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden. Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen. Zum Beispiel */home/user1* unter Linux oder *C:\Users\user1* unter Windows.

### <a name="project-specific-tooling"></a>Projektspezifische Tools

Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.

### <a name="nugetconfig-differences"></a>Unterschiede bei „nuget.config“

Das Verhalten des Befehls `dotnet restore` wird durch Einstellungen in der *nuget.config*-Datei (falls vorhanden) beeinflusst. Das Festlegen von `globalPackagesFolder` in *nuget.config* platziert z. B. die wiederhergestellten NuGet-Pakete in den angegebenen Ordner. Dies ist eine Alternative zur Angabe der Option `--packages` im `dotnet restore`-Befehl. Weitere Informationen finden Sie in der [Referenz zu „nuget.config“](/nuget/schema/nuget-config-file).

Es gibt drei bestimmte Einstellungen, die von `dotnet restore` ignoriert werden:

- [bindingRedirects](/nuget/schema/nuget-config-file#bindingredirects-section)

  Bindungsumleitungen funktionieren nicht mit `<PackageReference>`-Elementen, und .NET Core unterstützt nur `<PackageReference>`-Elemente für NuGet-Pakete.

- [solution](/nuget/schema/nuget-config-file#solution-section)

  Diese Einstellung ist spezifisch für Visual Studio und gilt nicht für .NET Core. .NET Core verwendet keine `packages.config`-Datei, aber stattdessen `<PackageReference>`-Elemente für NuGet-Pakete.

- [trustedSigners](/nuget/schema/nuget-config-file#trustedsigners-section)

  Diese Einstellung ist nicht anwendbar, da [NuGet noch keine plattformübergreifende Überprüfung](https://github.com/NuGet/Home/issues/7939) vertrauenswürdiger Pakete unterstützt.

## <a name="arguments"></a>Argumente

- **`ROOT`**

  Optionaler Pfad zur wiederherzustellenden Projektdatei.

## <a name="options"></a>Optionen

- **`--configfile <FILE>`**

  Die NuGet-Konfigurationsdatei (*nuget.config*) für den Wiederherstellungsvorgang.

- **`--disable-parallel`**

  Deaktiviert paralleles Erstellen von mehreren Projekten.

- **`--force`**

  Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.

- **`--force-evaluate`**

  Erzwingt die Neubewertung aller Abhängigkeiten bei der Wiederherstellung, selbst wenn bereits eine Sperrdatei vorhanden ist.

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

- **`--ignore-failed-sources`**

  Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.

- **`--interactive`**

  Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen). Ab .NET Core 2.1.400.

- **`--lock-file-path <LOCK_FILE_PATH>`**

  Ausgabespeicherort, in den die Projektsperrdatei geschrieben wird. Standardmäßig ist dies *PROJECT_ROOT\packages.lock.json*.

- **`--locked-mode`**

  Lassen Sie keine Aktualisierung der Projektsperrdatei zu.

- **`--no-cache`**

  Gibt an, dass keine HTTP-Anforderungen zwischengespeichert werden

- **`--no-dependencies`**

  Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

- **`--packages <PACKAGES_DIRECTORY>`**

  Gibt das Verzeichnis für wiederhergestellte Pakete an.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Gibt eine Laufzeit für die Wiederherstellung des Pakets an. Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.

- **`-s|--source <SOURCE>`**

  Gibt den URI der NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist. Diese Einstellung überschreibt alle Quellen, die in den *nuget.config*-Dateien angegeben sind. Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.

- **`--use-lock-file`**

  Ermöglicht das Generieren und Verwenden einer Projektsperrdatei bei der Wiederherstellung.

- **`-v|--verbosity <LEVEL>`**

  Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `minimal`sein.

## <a name="examples"></a>Beispiele

- Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:

  ```dotnetcli
  dotnet restore
  ```

- Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit detaillierter Ausgabe:

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
