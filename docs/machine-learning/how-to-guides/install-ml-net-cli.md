---
title: Installieren des ML.NET-Befehlszeilenschnittstellen-Tools (CLI)
description: Übersicht und Installation des ML.NET-Befehlszeilenschnittstellen-Tools (CLI)
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: feeb4832b5bbd39f28ac2c6f6caa40d60b4f3aa9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977080"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a>Installieren des ML.NET-Befehlszeilenschnittstellen-Tools (CLI)

Die ML.NET-CLI (Befehlszeilenschnittstelle) ist ein Tool, das Sie über jede Eingabeaufforderung (Windows, Mac oder Linux) ausführen können, um qualitativ hochwertige ML.NET-Modelle und Quellcode basierend auf von Ihnen bereitgestellten Trainingsdatasets zu generieren.

> [!NOTE]
> Dieses Thema bezieht sich auf die ML.NET-CLI und ML.NET AutoML, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.

## <a name="pre-requisites"></a>Voraussetzungen

- [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- (Optional) [Visual Studio 2017 oder 2019](https://visualstudio.microsoft.com/vs/)

Sie können die generierten C#-Codeprojekte entweder mit Visual Studio F5 oder mit `dotnet run` ausführen (.NET Core-CLI).

Hinweis: Wenn nach der Installation von [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) der Befehl `dotnet tool` nicht funktioniert, melden Sie sich von Windows ab und erneut wieder an.

## <a name="install"></a>Installieren

Die ML.NET-CLI wird wie jedes andere globale .NET-Tool installiert. Sie verwenden den .NET Core-CLI-Befehl `dotnet tool install`.

Im folgenden Beispiel wird gezeigt, wie eine ML.NET-CLI im standardmäßigen NuGet-Feedspeicherort installiert wird:

```dotnetcli
dotnet tool install -g mlnet
```

Wenn das Tool nicht installiert werden kann (d.h. wenn es im standardmäßigen NuGet-Feed nicht verfügbar ist), werden Fehlermeldungen angezeigt. Stellen Sie sicher, dass die erwarteten Feeds überprüft werden.

Wenn die Installation erfolgreich abgeschlossen wurde, wird eine Meldung angezeigt, die den Befehl zum Aufrufen des Tools und die installierte Version ähnlich wie im folgenden Beispiel anzeigt:

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

Sie können bestätigen, dass die Installation erfolgreich war, indem Sie den folgenden Befehl eingeben:

```console
mlnet
```

Es sollte die Hilfe zu den verfügbaren Befehlen für das mlnet-Tool angezeigt werden, wie z.B. den Befehl „auto-train“.

## <a name="install-a-specific-release-version"></a>Installieren einer bestimmten Releaseversion

Wenn Sie versuchen, eine Vorabversion oder eine spezifische Version des Tools zu installieren, können Sie das [Framework](../../standard/frameworks.md) im folgenden Format angeben:

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

Sie können auch überprüfen, ob das Paket ordnungsgemäß installiert ist, indem Sie den folgenden Befehl eingeben:

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a>Deinstallieren des CLI-Pakets

Geben Sie den folgenden Befehl ein, um das Paket über Ihren lokalen Computer zu deinstallieren:

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a>Aktualisieren des CLI-Pakets

Geben Sie den folgenden Befehl ein, um das Paket über Ihren lokalen Computer zu aktualisieren:

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a>Einrichten der CLI-Empfehlungen (tabellarische automatische Vervollständigung)

Da die ML.NET-CLI auf `System.CommandLine` basiert, ist die Unterstützung für die tabellarische automatische Vervollständigung integriert.

Ein Beispiel für die Funktionsweise der tabellarischen automatischen Vervollständigung sehen Sie in der folgenden Animation:

![Bild](./media/cli-tab-completion.gif)

Die tabellarische automatische Vervollständigung (Parameterempfehlungen) funktioniert für *Windows PowerShell* und *macOS/Linux-Bash* aber nicht unter *Windows-CMD*.

Um die Funktion zu aktivieren, muss der Endbenutzer in der aktuellen Vorschauversion einmal pro Shell einige Schritte ausführen, wie nachfolgend beschrieben. Danach funktionieren Vervollständigungen für alle Anwendungen, die mit `System.CommandLine` geschrieben wurden, wie z.B. ML.NET-CLI.

Auf dem Computer, auf dem Sie die Vervollständigung aktivieren möchten, müssen Sie zwei Schritte ausführen.

1. Installieren Sie das globale `dotnet-suggest`-Tool, indem Sie den folgenden Befehl ausführen:

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. Fügen Sie das entsprechende Shim-Skript zu Ihrem Shell-Profil hinzu. Möglicherweise müssen Sie eine Shell-Profildatei erstellen. Das Shim-Skript leitet Vervollständigungsanforderungen von Ihrer Shell an das `dotnet-suggest`-Tool weiter, das an die entsprechende `System.CommandLine`-basierte Anwendung delegiert.

    - Fügen Sie für Bash den Inhalt von [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) zu `~/.bash_profile` hinzu.

    - Fügen Sie für PowerShell den Inhalt von [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) zu Ihrem PowerShell-Profil hinzu. Den erwarteten Pfad zu Ihrem PowerShell-Profil finden Sie, indem Sie den folgenden Befehl in Ihrer Konsole ausführen:

    ```console
    echo $profile
    ```

(Für die anderen Shells können Sie nach einem [Problem](https://github.com/dotnet/System.CommandLine/issues) [suchen](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) oder ein neues erstellen.)

## <a name="installation-directory"></a>Installationsverzeichnis

Die ML.NET-CLI kann im Standardverzeichnis oder an einem spezifischen Speicherort installiert werden. Die Standardverzeichnisse sind:

| Betriebssystem          | Pfad                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Diese Speicherorte werden dem Pfad des Benutzers hinzugefügt, wenn das SDK zum ersten Mal ausgeführt wird, damit dort installierte globale Tools direkt aufgerufen werden können.

Beachten Sie, dass die globalen Tools benutzerspezifisch gespeichert werden und nicht global auf dem Computer. Deshalb können Sie kein globales Tool installieren, das für alle Benutzer auf dem Computer verfügbar ist. Das Tool ist nur für jedes Benutzerprofil verfügbar, auf denen das Tool installiert wurde.

Globale Tools können auch in einem spezifischen Verzeichnis installiert werden. Wenn sie in einem spezifischen Verzeichnis installiert werden, muss der Benutzer sicherstellen, dass der Befehl verfügbar ist, indem das Verzeichnis in den Pfad eingefügt, der Befehl mit dem angegebenen Verzeichnis aufgerufen oder das Tool aus dem angegebenen Verzeichnis aufgerufen wird.
In diesem Fall fügt die .NET Core-CLI diesen Speicherort nicht automatisch der Umgebungsvariable „PATH“ hinzu.

## <a name="see-also"></a>Siehe auch

- [Tutorial „Erste Schritte mit dem ML.NET CLI-Tool“](../tutorials/mlnet-cli.md)
- [Vorgehensweise: Automatisches Trainieren von Modellen mit dem ML.NET CLI-Tool](../automate-training-with-cli.md)
- [Referenzhandbuch für den „auto-train“-Befehl in der ML.NET-CLI](../reference/ml-net-cli-reference.md)
- [Telemetrie in der ML.NET-CLI](../resources/ml-net-cli-telemetry.md)
