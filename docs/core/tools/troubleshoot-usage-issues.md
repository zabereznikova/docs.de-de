---
title: Behandlung von Problemen bei der Nutzung von .NET Core-Tools
description: Informieren Sie sich über allgemeine Probleme beim Ausführen von .NET Core-Tools sowie über mögliche Lösungen.
author: kdollard
ms.date: 02/14/2020
ms.openlocfilehash: ab5d1be8f201ea283f8537f18886feab46157127
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543273"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a>Behandlung von Problemen bei der Nutzung von .NET Core-Tools

Beim Installieren oder Ausführen eines globalen oder lokalen .NET Core-Tools können Probleme auftreten. In diesem Artikel werden die allgemeinen Grundursachen und einige mögliche Lösungen beschrieben.

## <a name="installed-net-core-tool-fails-to-run"></a>Ausführung eines installierten .NET Core-Tools schlägt fehl

Wenn die Ausführung eines .NET Core-Tools fehlschlägt, ist sehr wahrscheinlich eines der folgenden Probleme aufgetreten:

* Die ausführbare Datei für das Tool wurde nicht gefunden.
* Die richtige Version der .NET Core-Runtime wurde nicht gefunden.

### <a name="executable-file-not-found"></a>Ausführbare Datei nicht gefunden

Wenn die ausführbare Datei nicht gefunden wird, wird eine Meldung angezeigt, die in etwa wie folgt lautet:

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

Der Name der ausführbaren Datei bestimmt, wie Sie das Tool aufrufen. Das Format wird in der folgenden Tabelle beschrieben:

| Format der ausführbaren Datei  | Aufrufformat   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* Globale Tools

    Globale Tools können im Standardverzeichnis oder an einem spezifischen Speicherort installiert werden. Die Standardverzeichnisse sind:

    | Betriebssystem          | Pfad                          |
    |-------------|-------------------------------|
    | Linux/macOS | `$HOME/.dotnet/tools`         |
    | Windows     | `%USERPROFILE%\.dotnet\tools` |

    Prüfen Sie beim Ausführen eines globalen Tools, ob die Umgebungsvariable `PATH` auf Ihrem Computer den Pfad enthält, unter dem Sie das globale Tool installiert haben, und ob sich die ausführbare Datei in diesem Verzeichnis befindet.

    Die .NET Core-CLI versucht bei der ersten Verwendung, die Standardspeicherorte der Umgebungsvariable „PATH“ hinzuzufügen. Es gibt jedoch einige Szenarios, in denen der Speicherort der Variablen „PATH“ nicht automatisch hinzugefügt werden kann, sodass Sie „PATH“ bearbeiten müssen, um die Variable für folgende Fälle zu konfigurieren:

  * Wenn Sie Linux verwenden und das .NET Core SDK mit *TAR.GZ*-Dateien anstelle von „apt-get“ oder „rpm“ installiert haben.
  * Wenn Sie macOS 10.15 „Catalina“ oder höhere Versionen verwenden.
  * Wenn Sie macOS 10.14 „Mojave“ oder frühere Versionen verwenden und das .NET Core SDK mit *TAR.GZ*-Dateien statt mit *PKG*-Dateien installiert haben.
  * Wenn Sie das .NET Core 3.0 SDK installiert und die Umgebungsvariable `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` auf `false` festgelegt haben.
  * Wenn Sie .NET Core 2.2 SDK oder frühere Versionen installiert und die Umgebungsvariable `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` auf `true` festgelegt haben.

  Weitere Informationen finden Sie unter [.NET Core-Tools](global-tools.md).

* Lokale Tools

  Prüfen Sie beim Ausführen eines lokalen Tools, ob im aktuellen Verzeichnis oder in einem der übergeordneten Verzeichnisse eine Manifestdatei mit dem Namen *dotnet-tools.json* vorhanden ist. Diese Datei kann sich auch in einem Ordner mit dem Namen *CONFIG* in der Projektordnerhierarchie statt im Stammverzeichnis befinden. Wenn *dotnet-tools.json* vorhanden ist, öffnen Sie die Datei und überprüfen Sie, ob das Tool enthalten ist, das Sie ausführen möchten. Wenn die Datei keinen Eintrag für `"isRoot": true` enthält, suchen Sie weiter oben in der Dateihierarchie nach weiteren Manifestdateien des Tools.

  Beim Ausführen eines .NET Core-Tools, das mit einem angegebenen Pfad installiert wurde, müssen Sie bei Verwendung des Tools diesen Pfad angeben. Beispiel für die Verwendung eines mit einem Toolpfad installierten Tools:

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a>Runtime nicht gefunden

.NET Core-Tools sind [Framework-abhängige Anwendungen](../deploying/index.md#publish-runtime-dependent), d. h. sie sind von der auf Ihrem Computer installierten .NET Core-Runtime abhängig. Wenn die erwartete Runtime nicht gefunden wurde, orientieren sie sich an den normalen Regeln für das Rollforward der .NET Core-Runtime, zum Beispiel:

* Eine Anwendung wird auf das neueste Patchrelease der angegebenen Haupt- und Nebenversion gebracht.
* Wenn keine übereinstimmende Runtime mit einer übereinstimmenden Haupt- und Nebenversion vorhanden ist, wird die nächsthöhere Nebenversion verwendet.
* Ein Rollforward findet nicht zwischen Vorschauversionen der Runtime oder Vorschauversionen und Releaseversionen statt. Daher müssen .NET Core-Tools, die mit Vorschauversionen erstellt wurden, vom Autor neu erstellt, veröffentlicht und installiert werden.

Rollforward findet in zwei gängigen Szenarios nicht standardmäßig statt:

* Es sind nur frühere Versionen der Runtime verfügbar. Beim Rollforward werden nur höhere Versionen der Runtime ausgewählt.
* Es sind nur höhere Hauptversionen der Runtime verfügbar. Mit dem Rollforward werden die Grenzen von Hauptversionen nicht überschritten.

Wenn eine Anwendung keine entsprechende Runtime finden kann, schlägt die Ausführung fehl, und ein Fehler wird gemeldet.

Sie können die auf Ihrem Computer installierten .NET Core-Runtimes mit einem der folgenden Befehle anzeigen:

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

Wenn Sie der Meinung sind, dass das Tool die von Ihnen installierte Runtimeversion unterstützen sollte, können Sie den Autor des Tools fragen, ob er die Versionsnummer aktualisieren oder mehrere Ziele zuweisen kann. Nachdem das Toolpaket erneut kompiliert und auf NuGet mit einer aktualisierten Versionsnummer veröffentlicht wurde, können Sie Ihre Kopie aktualisieren. Bis dies geschehen ist, können Sie eine Version der Runtime installieren, die mit dem gewünschten Tool verwendet werden kann. Wenn Sie eine bestimmte .NET Core-Runtimeversion herunterladen möchten, besuchen Sie die [.NET Core-Downloadseite](https://dotnet.microsoft.com/download/dotnet-core).

Wenn Sie das .NET Core SDK an einem nicht standardmäßigen Speicherort installieren, müssen Sie die Umgebungsvariable `DOTNET_ROOT` auf das Verzeichnis festlegen, das die ausführbare Datei `dotnet` enthält.

## <a name="net-core-tool-installation-fails"></a>Fehler bei der Installation von .NET Core-Tools

Es gibt verschiedene Gründe, warum bei der Installation eines globalen oder lokalen .NET Core-Tools möglicherweise ein Fehler auftritt. Wenn bei der Installation eines Tools ein Fehler auftritt, wird eine Meldung angezeigt, die in etwa so lautet:

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

Um diese Fehler zu diagnostizieren, werden dem Benutzer neben der vorherigen Meldung auch NuGet-Meldungen angezeigt. Mithilfe der NuGet-Meldung können Sie das Problem möglicherweise identifizieren.

### <a name="package-naming-enforcement"></a>Durchsetzung der Paketbenennung

Microsoft hat den Leitfaden zur Paket-ID für Tools geändert, was dazu führt, dass eine Reihe von Tools mit dem vorhergesagten Namen nicht gefunden werden. Der neue Leitfaden besagt, dass alle Microsoft-Tools das Präfix „Microsoft.“ enthalten müssen. Dieses Präfix ist reserviert und kann nur für Pakete verwendet werden, die mit einem autorisierten Microsoft-Zertifikat signiert sind.

In der Übergangszeit haben einige Microsoft-Tools die alte Form der Paket-ID, während andere die neue Form aufweisen:

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

Bei aktualisierten Paket-IDs müssen Sie zum Abrufen der aktuellen Updates die neue Paket-ID verwenden. Pakete mit dem vereinfachten Toolnamen gelten als veraltet.

### <a name="preview-releases"></a>Vorschaureleases

* Beim Installieren eines Vorschaureleases geben Sie die Version ohne die `--version`-Option an.

.NET Core-Tools, die in einer Vorschauversion vorliegen, müssen zur Kennzeichnung dieses Umstands mit einem Teil des Namens angegeben werden. Dabei müssen Sie nicht die gesamte Vorschauversion angeben. Sofern die Versionsnummern im erwarteten Format vorliegen, können Sie das folgende Beispiel oder Ähnliches verwenden:

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a>Das Paket ist kein .NET Core-Tool

* Es wurde ein NuGet-Paket mit diesem Namen gefunden. Dabei handelt es sich jedoch nicht um ein .NET Core-Tool.

Wenn Sie ein NuGet-Paket installieren, bei dem es sich nicht um ein .NET Core-Tool, sondern um ein normales NuGet-Paket handelt, wird eine Fehlermeldung angezeigt, die in etwa wie folgt lautet:

> NU1212: Ungültige Projekt-/Paket-Kombination für `<ToolName>`. Der DotnetToolReference-Projektstil darf nur Verweise vom Typ „DotnetTool“ enthalten.

### <a name="nuget-feed-cant-be-accessed"></a>Auf den NuGet-Feed kann nicht zugegriffen werden

* Auf den erforderlichen NuGet-Feed kann möglicherweise aufgrund eines Problems mit der Internetverbindung nicht zugegriffen werden.

Für die Installation des Tools muss jedoch auf den NuGet-Feed zugegriffen werden, der das Toolpaket enthält. Ist dies nicht möglich, schlägt die Installation fehl. Sie können Feeds mit `nuget.config` ändern, eine bestimmte `nuget.config`-Datei anfordern oder mit dem `--add-source`-Switch zusätzliche Feeds angeben. NuGet löst standardmäßig für jeden Feed, auf den nicht zugegriffen werden kann, einen Fehler aus. Mit dem `--ignore-failed-sources`-Flag können diese nicht erreichbaren Quellen übersprungen werden.

### <a name="package-id-incorrect"></a>Paket-ID ist fehlerhaft

* Der Name des Tools wurde falsch eingegeben.

Eine häufige Ursache für Fehler ist ein fehlerhafter Toolname. Ursache hierfür kann ein Tippfehler oder die Tatsache sein, dass das Tool verschoben wurde oder als veraltet gilt. Bei Tools auf NuGet.org können Sie sicherstellen, dass der Name stimmt, indem Sie unter NuGet.org nach dem Tool suchen und den Installationsbefehl kopieren.

## <a name="see-also"></a>Siehe auch

* [.NET Core-Tools](global-tools.md)
