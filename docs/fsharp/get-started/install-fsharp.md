---
title: Installieren von f#
description: Erfahren Sie, wie Sie F#-basierend auf Ihrer Umgebung installieren.
ms.date: 07/03/2018
ms.openlocfilehash: 142265a95e1d3ee1603a89f650a24c6a45709181
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37878845"
---
# <a name="install-f"></a>Installieren von f# #

Sie können f# auf verschiedene Arten, abhängig von Ihrer Umgebung installieren.

## <a name="install-f-with-visual-studio"></a>F# mit Visual Studio installieren.

Wenn Sie herunterladen werden [Visual Studio](https://visualstudio.microsoft.com/) zum ersten Mal wird es zunächst Visual Studio-Installer installieren. Installieren Sie die entsprechende SKU von Visual Studio über den Installer. Wenn Sie bereits installiert haben, klicken Sie auf **ändern**.

Als Nächstes sehen Sie, eine Liste von Workloads. Wählen Sie **ASP.NET und Webentwicklung**, die f#-Unterstützung, Unterstützung für .NET Core, installiert und F#-Unterstützung für ASP.NET Core-Projekte.

Klicken Sie anschließend **ändern** in der unteren rechten Ecke.  Dadurch wird alles, was installiert, die Sie ausgewählt haben. Anschließend können Sie Visual Studio 2017 mit F#-sprachunterstützung öffnen, indem Sie auf **starten**.

## <a name="install-f-with-visual-studio-for-mac"></a>Installieren von f# in Visual Studio für Mac

F# ist standardmäßig unter installiert [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/), unabhängig davon, welche Konfiguration Sie auswählen.

Nachdem die Installation abgeschlossen ist, wählen Sie "Starten Sie Visual Studio". Sie können es auch über den Finder unter MacOS starten.

## <a name="install-f-with-visual-studio-code"></a>Installieren von f# mit Visual Studio Code

Benötigen Sie [Git-Installation](https://git-scm.com/download) und verfügbar ist, auf dem Weg zur Stellen der Projektvorlagen das Projekt in Ionide verwenden. Sie können überprüfen, dass es ordnungsgemäß, durch Eingabe installiert ist `git --version` an einer Eingabeaufforderung, und drücken **EINGABETASTE**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

Ionide verwendet [Mono](http://www.mono-project.com). Die einfachste Möglichkeit zum Installieren von Mono unter MacOS ist über Homebrew. Geben Sie einfach Folgendes in Ihrem Terminal ein:

```console
brew install mono
```

Außerdem müssen Sie installieren die [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

Unter Linux verwendet Ionide auch [Mono](https://www.mono-project.com). Wenn Sie sich unter Debian oder Ubuntu sind, können Sie Folgendes:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Außerdem müssen Sie installieren die [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Wenn Sie Windows verwenden, müssen Sie [Visual Studio mit f#-Unterstützung installieren](#install-f-with-visual-studio). Dadurch werden alle erforderlichen Komponenten zum Schreiben, kompilieren und Ausführen von f#-Code installiert.

Außerdem müssen Sie installieren die [.NET Core SDK](https://www.microsoft.com/net/download/).

---

Sie müssen dann [Visual Studio Code](https://code.visualstudio.com) installiert.

Klicken Sie dann auf das Symbol "Erweiterungen" und suchen Sie nach "Ionide":

Erforderlich für f#-Unterstützung in Visual Studio Code ist die einzige-Plug-in [Ionide-Fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Allerdings können Sie auch installieren [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) abzurufenden [FAKE](https://fsharp.github.io/FAKE/) unterstützen und [Ionide-Paket-Abhängigkeits](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) abzurufenden [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) unterstützen. Falsche und Paket-Abhängigkeits sind zusätzliche F#-Community-Tools für Projekte erstellen und Verwalten von Abhängigkeiten, bzw.