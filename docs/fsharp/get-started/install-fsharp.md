---
title: Installieren von F#
description: Informationen zum Installieren F# basierend auf Ihrer Umgebung.
ms.date: 08/28/2018
ms.openlocfilehash: 792c61c0522cd4d0c68a64572f2892ce33f71ea6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017019"
---
# <a name="install-f"></a>Installieren von F\#

Sie können F# auf verschiedene Arten, abhängig von Ihrer Umgebung installieren.

## <a name="install-f-with-visual-studio"></a>Installieren Sie F# mit Visual Studio

Wenn Sie herunterladen werden [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) zum ersten Mal wird es zunächst Visual Studio-Installer installieren. Installieren Sie die entsprechende SKU von Visual Studio über den Installer. Wenn Sie bereits installiert haben, klicken Sie auf **ändern**.

Als Nächstes sehen Sie, eine Liste von Workloads. Wählen Sie **ASP.NET und Webentwicklung** der F#-Unterstützung und Unterstützung für ASP.NET Core-Projekte für .NET Core installieren.

Klicken Sie anschließend **ändern** in der unteren rechten Ecke.  Dadurch wird alles, was installiert, die Sie ausgewählt haben. Anschließend können Sie Visual Studio 2017 mit öffnen F# sprachunterstützung durch Klicken auf **starten**.

## <a name="install-f-with-visual-studio-for-mac"></a>Installieren von F# in Visual Studio für Mac

F#wird standardmäßig unter installiert [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), unabhängig davon, welche Konfiguration Sie auswählen.

Nachdem die Installation abgeschlossen ist, wählen Sie "Starten Sie Visual Studio". Sie können es auch über den Finder unter MacOS starten.

## <a name="install-f-with-visual-studio-code"></a>Installieren von F# mit Visual Studio Code

Sie benötigen [Git-Installation](https://git-scm.com/download) und verfügbar ist, auf dem Weg zur Stellen verwenden der Projektvorlagen das Projekt. Sie können überprüfen, dass es ordnungsgemäß, durch Eingabe installiert ist `git --version` an einer Eingabeaufforderung, und drücken **EINGABETASTE**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen. Die einfachste Möglichkeit zum Installieren von Mono unter MacOS ist über Homebrew. Geben Sie einfach Folgendes in Ihrem Terminal ein:

```console
brew install mono
```

Installieren Sie auch die [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) dient zur [F# Interactive](../tutorials/fsharp-interactive/index.md) unterstützen. Wenn Sie sich unter Debian oder Ubuntu sind, können Sie Folgendes:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Installieren Sie auch die [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Installieren Sie [Visual Studio mit F#-Unterstützung](#install-f-with-visual-studio). Dadurch werden alle erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von F#-Code installiert.

Installieren Sie auch die [.NET Core SDK](https://www.microsoft.com/net/download/).

---

Sie müssen dann [Visual Studio Code](https://code.visualstudio.com) installiert.

Klicken Sie dann auf das Symbol "Erweiterungen" und suchen Sie nach "Ionide":

Erforderlich für F#-Unterstützung in Visual Studio Code ist die einzige-Plug-in [Ionide-Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Allerdings können Sie auch installieren [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) abzurufenden [FAKE](https://fsharp.github.io/FAKE/) unterstützen und [Ionide-Paket-Abhängigkeits](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) abzurufenden [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) unterstützen. Falsche und Paket-Abhängigkeits sind zusätzliche F# communitytools für die Projekte erstellen und Verwalten von Abhängigkeiten, bzw.
