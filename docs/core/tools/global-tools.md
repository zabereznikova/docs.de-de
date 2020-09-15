---
title: .NET Core-Tools
description: Informationen zum Installieren, Verwenden, Aktualisieren und Entfernen von .NET Core-Tools. In diesem Artikel werden globale, Toolpfad- und lokale Tools vorgestellt.
author: KathleenDollard
ms.topic: how-to
ms.date: 02/12/2020
ms.openlocfilehash: 08277ed791036201d1dfa30c21799db1c21a924e
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598134"
---
# <a name="how-to-manage-net-core-tools"></a>Verwalten von .NET Core-Tools

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

Ein .NET Core-Tool ist ein spezielles NuGet-Paket, das eine Konsolenanwendung enthält. Ein Tool kann auf folgende Weisen auf dem Computer installiert werden:

* Als globales Tool.

  Die Binärdateien für das Tool werden in einem Standardverzeichnis installiert, das der Umgebungsvariablen PATH hinzugefügt wird. Sie können das Tool aus einem beliebigen Verzeichnis auf dem Computer aufrufen, ohne seinen Speicherort anzugeben. Eine Version eines Tools wird für alle Verzeichnisse auf dem Computer verwendet.

* Als globales Tool an einem benutzerdefinierten Speicherort (auch „Toolpfadtool“ genannt).

  Die Binärdateien für das Tool werden an einem von Ihnen angegebenen Speicherort installiert. Sie können das Tool im Installationsverzeichnis aufrufen oder indem Sie das Verzeichnis mit dem Befehlsnamen angeben oder das Verzeichnis zur Umgebungsvariablen PATH hinzufügen. Eine Version eines Tools wird für alle Verzeichnisse auf dem Computer verwendet.

* Als lokales Tool (ab .NET Core SDK 3.0).

  Die Binärdateien des Tools werden in einem Standardverzeichnis installiert. Sie rufen das Tool im Installationsverzeichnis oder einem seiner Unterverzeichnisse auf. Verschiedene Verzeichnisse können unterschiedliche Versionen desselben Tools verwenden.
  
  Die .NET-CLI nutzt Manifestdateien, um nachzuverfolgen, welche Tools lokal in einem Verzeichnis installiert sind. Wenn die Manifestdatei im Stammverzeichnis eines Quellcoderepositorys gespeichert ist, kann ein Mitwirkender das Repository klonen und einen einzelnen .NET Core-CLI-Befehl aufrufen, mit dem alle in den Manifestdateien aufgeführten Tools installiert werden.

> [!IMPORTANT]
> .NET Core-Tools werden mit voller Vertrauenswürdigkeit ausgeführt. Installieren Sie .NET Core-Tools nur von Autoren, denen Sie vertrauen.

## <a name="find-a-tool"></a>Suchen eines Tools

Derzeit bietet .NET Core keine Suchfunktion für Tools. Es folgen einige Möglichkeiten, Tools zu finden:

* Durchsuchen Sie die [NuGet](https://www.nuget.org)-Website mithilfe des Pakettypfilters „.NET tool“. Weitere Informationen finden Sie unter [Finding and choosing packages (Suchen und Auswählen von Paketen)](/nuget/consume-packages/finding-and-choosing-packages).
* Sehen Sie sich die Liste der Tools im GitHub-Repository [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) an.
* Verwenden Sie [ToolGet](https://www.toolget.net/), um nach .NET-Tools zu suchen.
* Sehen Sie sich den Quellcode der vom ASP.NET Core-Team im [GitHub-Repository dotnet/aspnetcore im Verzeichnis „Tools“](https://github.com/dotnet/aspnetcore/tree/master/src/Tools) erstellten Tools an.
* Weitere Informationen zu Diagnosetools finden Sie unter [Globale .NET Core-dotnet-Diagnosetools](../diagnostics/index.md#net-core-diagnostic-global-tools).

## <a name="check-the-author-and-statistics"></a>Überprüfen des Autors und der Statistiken

Da .NET Core-Tools mit voller Vertrauenswürdigkeit ausgeführt und globale Tools der Umgebungsvariablen PATH hinzugefügt werden, können sie sehr leistungsfähig sein. Laden Sie keine Tools von Personen herunter, denen Sie nicht vertrauen.

Wenn das Tool auf NuGet gehostet wird, können Sie den Autor und seine Statistiken überprüfen, indem Sie nach dem Tool suchen.

## <a name="install-a-global-tool"></a>Installieren eines globalen Tools

Um ein Tool als globales Tool zu installieren, verwenden Sie, wie im folgenden Beispiel gezeigt, mit [dotnet tool install](dotnet-tool-install.md) die Option `-g` oder `--global`:

```dotnetcli
dotnet tool install -g dotnetsay
```

Die Ausgabe zeigt den zum Aufrufen des Tools verwendeten Befehl und die installierte Version, ähnlich wie im folgenden Beispiel:

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

Der Standardspeicherort der Binärdateien eines Tools hängt vom Betriebssystem ab:

| Betriebssystem          | Pfad                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Dieser Speicherort wird beim ersten Ausführen des SDK dem Pfad des Benutzers hinzugefügt, sodass globale Tools in jedem beliebigen Verzeichnis aufgerufen werden können, ohne dass der Speicherort des Tools angegeben werden muss.

Der Zugriff auf Tools ist benutzerspezifisch und gilt nicht global auf dem Computer. Ein globales Tool ist nur für den Benutzer verfügbar, der das Tool installiert hat.

### <a name="install-a-global-tool-in-a-custom-location"></a>Installieren eines globalen Tools an einem benutzerdefinierten Speicherort

Um ein Tool als globales Tool an einem benutzerdefinierten Speicherort zu installieren, verwenden Sie, wie in den folgenden Beispielen gezeigt, mit [dotnet tool install](dotnet-tool-install.md) die Option `--tool-path`.

Unter Windows:

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

Unter Linux oder macOS:

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

Das .NET Core SDK fügt diesen Speicherort nicht automatisch der Umgebungsvariablen PATH hinzu. Zum [Aufrufen eines Toolpfadtools](#invoke-a-tool-path-tool) müssen Sie sicherstellen, dass der Befehl verfügbar ist, indem Sie eine der folgenden Methoden verwenden:

* Fügen Sie das Installationsverzeichnis der Umgebungsvariablen PATH hinzu.
* Geben Sie den vollständigen Pfad zum Tool an, wenn Sie es aufrufen.
* Rufen das Tool im Installationsverzeichnis auf.

## <a name="install-a-local-tool"></a>Installieren eines lokalen Tools

**Gilt ab .NET Core 3.0 SDK.**

Um ein Tool nur für den lokalen Zugriff (für das aktuelle Verzeichnis und Unterverzeichnisse) zu installieren, muss es der Manifestdatei des Tools hinzugefügt werden. Führen Sie den Befehl `dotnet new tool-manifest` aus, um eine Manifestdatei für das Tool zu erstellen:

```dotnetcli
dotnet new tool-manifest
```

Mit diesem Befehl wird im Verzeichnis *.config* eine Manifestdatei mit dem Namen *dotnet-tools.json* erstellt. Um der Manifestdatei ein lokales Tool hinzuzufügen, verwenden Sie den Befehl [dotnet tool install](dotnet-tool-install.md) **ohne** die Optionen `--global` und `--tool-path`, wie im folgenden Beispiel gezeigt:

```dotnetcli
dotnet tool install dotnetsay
```

Die Befehlsausgabe zeigt, in welcher Manifestdatei sich das neu installierte Tool befindet, ähnlich wie im folgenden Beispiel:

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

Das folgende Beispiel zeigt eine Manifestdatei, in der zwei lokale Tools installiert sind:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

In der Regel fügen Sie ein lokales Tool zum Stammverzeichnis des Repositorys hinzu. Nach dem Einchecken der Manifestdatei im Repository erhalten Entwickler, die Code aus dem Repository auschecken, die neueste Manifestdatei. Um alle in der Manifestdatei aufgeführten Tools zu installieren, führen sie den Befehl `dotnet tool restore` aus:

```dotnetcli
dotnet tool restore
```

Die Ausgabe gibt an, welche Tools wiederhergestellt wurden:

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a>Installieren einer bestimmten Toolversion

Um eine Vorab- oder bestimmte Version eines Tools zu installieren, geben Sie die Versionsnummer mit der Option `--version` an, wie im folgenden Beispiel gezeigt:

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a>Verwenden eines Tools

Der Befehl zum Aufrufen eines Tools kann sich vom Namen des Pakets, das Sie installieren, unterscheiden. Um alle derzeit für den aktuellen Benutzer auf dem Computer installierten Tools anzuzeigen, führen Sie den Befehl [dotnet tool list](dotnet-tool-list.md) aus:

```dotnetcli
dotnet tool list
```

Die Ausgabe zeigt die Version und den Befehl jedes Tools, ähnlich wie im folgenden Beispiel:

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

Wie in diesem Beispiel gezeigt, enthält die Liste lokale Tools. Zum Anzeigen globaler Tools verwenden Sie die Option `--global`. Zum Anzeigen von Toolpfadtools wählen Sie die Option `--tool-path`.

### <a name="invoke-a-global-tool"></a>Aufrufen eines globalen Tools

Verwenden Sie für globale Tools den Tool-Befehl eigenständig. Wenn der Befehl beispielsweise `dotnetsay` oder `dotnet-doc` lautet, verwenden Sie Folgendes, um den Befehl aufzurufen:

```console
dotnetsay
dotnet-doc
```

Wenn der Befehl mit dem Präfix `dotnet-` beginnt, können Sie das Tool alternativ auch mit dem Befehl `dotnet` ohne das Präfix des tool-Befehls aufrufen. Wenn der Befehl z. B. `dotnet-doc` lautet, wird das Tool mit dem folgenden Befehl aufgerufen:

```dotnetcli
dotnet doc
```

Im folgenden Szenario können Sie jedoch nicht den Befehl `dotnet` verwenden, um ein globales Tool aufzurufen:

* Für ein globales Tool und ein lokales Tool gilt der gleiche Befehl mit dem Präfix `dotnet-`.
* Sie möchten das globale Tool in einem Verzeichnis aufrufen, das im Geltungsbereich des lokalen Tools liegt.

In diesem Fall rufen `dotnet doc` und `dotnet dotnet-doc` das lokale Tool auf. Um das globale Tool aufzurufen, verwenden Sie den Befehl eigenständig:

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a>Aufrufen eines Toolpfadtools

Um ein globales Tool aufzurufen, das mit der Option `tool-path` installiert wurde, stellen Sie sicher, dass der Befehl verfügbar ist, was [weiter oben in diesem Artikel](#install-a-global-tool-in-a-custom-location) erläutert wurde.

### <a name="invoke-a-local-tool"></a>Aufrufen eines lokalen Tools

Um ein lokales Tool aufzurufen, müssen Sie im Installationsverzeichnis den Befehl `dotnet` ausführen. Sie können die Langform (`dotnet tool run <COMMAND_NAME>`) oder Kurzform (`dotnet <COMMAND_NAME>`) verwenden, wie in den folgenden Beispielen gezeigt:

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

Wenn dem Befehl das Präfix `dotnet-` vorangestellt ist, können Sie das Präfix beim Aufruf des Tools einschließen oder weglassen. Wenn der Befehl z. B. `dotnet-doc` lautet, ruft eines der folgenden Beispiele das lokale Tool auf:

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a>Aktualisieren eines Tools

Das Aktualisieren eines Tools umfasst das Deinstallieren und Neuinstallieren mit der neuesten stabilen Version. Verwenden Sie zum Aktualisieren eines Tools den Befehl [dotnet tool update](dotnet-tool-update.md) mit derselben Option, die Sie auch zur Installation des Tools verwendet haben:

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

Bei einem lokalen Tool findet das SDK die erste Manifestdatei, die die Paket-ID enthält, indem es im aktuellen Verzeichnis und den übergeordneten Verzeichnissen eine Suche durchführt. Wenn es in keiner Manifestdatei keine solche Paket-ID gibt, fügt das SDK der nächstgelegenen Manifestdatei einen neuen Eintrag hinzu.

## <a name="uninstall-a-tool"></a>Deinstallieren eines Tools

Entfernen Sie ein Tool mit dem Befehl [dotnet tool uninstall](dotnet-tool-uninstall.md) mit der gleichen Option, die Sie zur Installation des Tools verwendet haben:

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path <packagename>
dotnet tool uninstall <packagename>
```

Bei einem lokalen Tool findet das SDK die erste Manifestdatei, die die Paket-ID enthält, indem es im aktuellen Verzeichnis und den übergeordneten Verzeichnissen eine Suche durchführt.

## <a name="get-help-and-troubleshoot"></a>Hilfe und Problembehandlung

Zum Abrufen einer Liste der verfügbaren `dotnet tool`-Befehle geben Sie den folgenden Befehl ein:

```dotnetcli
dotnet tool --help
```

Um Anweisungen zur Nutzung des Tools zu erhalten, geben Sie einen der folgenden Befehle ein, oder besuchen Sie die Website des Tools:

```dotnetcli
<command> --help
dotnet <command> --help
```

Wenn ein Tool nicht installiert oder ausgeführt werden kann, finden Sie unter [Behandlung von Problemen bei der Nutzung von .NET Core-Tools](troubleshoot-usage-issues.md) weitere Informationen.

## <a name="see-also"></a>Siehe auch

- [Tutorial: Erstellen eines .NET Core-Tool mithilfe der .NET Core-CLI](global-tools-how-to-create.md)
- [Tutorial: Erstellen und Verwenden eines globalen .NET Core-Tools mithilfe der .NET Core-CLI](global-tools-how-to-use.md)
- [Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI](local-tools-how-to-use.md)
